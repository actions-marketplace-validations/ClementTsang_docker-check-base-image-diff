# docker-check-base-image-diff

A Github Action that checks whether a derived image does not consist of a base image. Leverages
[`skopeo`](https://github.com/containers/skopeo) and [`jq`](https://stedolan.github.io/jq/).

Based on [lucacome's docker-image-update-checker](https://github.com/lucacome/docker-image-update-checker).

## Usage

Note that this action _assumes_ that `skopeo` is installed; this appears to be true for GitHub's Ubuntu runners.

### Inputs

#### `base-image`

A required argument, this represents the "base" image you want to check against.

As this is based on `skopeo`, it expects a string representing a container, and following a certain format
(e.g. `docker://rust:slim-buster`). For more information, see [the `skopeo` README](https://github.com/containers/skopeo#skopeo-).

### Outputs

A required argument, this represents the "derived" image you want to check.

As this is based on `skopeo`, it expects a string representing a container, and following a certain format
(e.g. `docker://rust:slim-buster`). For more information, see [the `skopeo` README](https://github.com/containers/skopeo#skopeo-).
