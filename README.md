# nextcloud-docker-smb

A Nextcloud Docker Image with SMB support built-in, based on the official [Nextcloud Community Images](https://github.com/nextcloud/docker).

This custom image only adds `smbclient` to the final image in accordance with the [official examples](https://github.com/nextcloud/docker/tree/master/.examples/dockerfiles/smb), it does not perform any other changes.

Our build process [hooks into the upstream repository](.github/actions/images.yml), so image tags and variants should always be up-to-date.

## Usage

To use the image, simply replace the source of the nextcloud image in your docker-compose/helm chart with either:

- `ghcr.io/spacebird-dev/nextcloud-docker-smb`
- or `quay.io/spacebird-dev/nextcloud-docker-smb`

All upstream tags except for `latest` and the `production` variants should be available.
