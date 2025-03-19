# Example

## Folder structure
```
auto
├── build
├── deploy
├── test
└── package
bin
├── shellcheck
├── terraform
└── yamllint
```

## Bin script
`bin/shellcheck`
```shell
#!/usr/bin/env bash
set -euo pipefail

exec docker run --rm --volume "$PWD:/mnt:ro" \
  "docker.io/koalaman/shellcheck:v0.9.0" \
  "$@"
```

## Auto script
`auto/dev-environment`
```shell
#!/usr/bin/env bash

# -e: Exit immediately if a command fails
# -u: Treat unset variables as an error
# -o pipefail: Return the exit code of the first failed command in a pipeline
set -euo pipefail

# Change to the root of the repository and ensure the all scripts are run from there
cd "$(dirname -- "$0")/.."

# If we are in a CI environment, use the CI image
if [ "${CI:-}" ] ; then
  IMAGE=[IMAGE_URI]
# Otherwise, build the dev image locally
else
  IMAGE="example:dev"

# This is typically used when you need the UID and GID of the current user for tasks
# such as setting file permissions, running commands as the correct user/group,
# or ensuring that processes are executed with the appropriate privileges.
  uid="$(id -u)"
  gid="$(id -g)"
  if [[ "${gid}" -lt 1000 ]]; then gid=1000; fi

  echo "--- Building dev environment" 1>&2
  docker build \
    --build-arg "UID=$uid" \
    --build-arg "GID=$gid" \
    --target dev \
    --tag "${IMAGE}" \
    .
fi

echo "+++ Running task inside dev environment" 1>&2
docker run \
  --rm \
  --interactive \
  --tty \
  --env AWS_ACCESS_KEY_ID \
  --env AWS_SECRET_ACCESS_KEY \
  --env AWS_SESSION_TOKEN \
  --env AWS_REGION \
  --env AWS_ACCOUNT \
  --env BUILDKITE_BUILD_NUMBER \
  --env BUILDKITE_BRANCH \
  -v "${PWD}:/app" \
  -w /app \
  "${IMAGE}" "${@-bash}"

```

`auto/lint-shell`
```shell
#!/usr/bin/env bash
set -euo pipefail

cd "$(dirname "$0")/.."
bin/shellcheck auto/* bin/*
```

`auto/test`
```shell
#!/usr/bin/env bash

set -euo pipefail
cd "$(dirname -- "$0")/.."

auto/dev-environment python3 -m pytest
```
