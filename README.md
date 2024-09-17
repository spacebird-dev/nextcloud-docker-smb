# nextcloud-docker-smb

A Nextcloud Docker Image with SMB support built-in, based on the official [Nextcloud Community Images](https://github.com/nextcloud/docker).

This custom image installs SMB support via php-smbclient, as suggested in the [official "full" examples](https://github.com/nextcloud/docker/tree/master/.examples/dockerfiles/smb), but it does not perform other changes, such as installing supervisord.
This results in a lightweight single-purpose image with full PHP-native SMB support that avoids issues popping up when [using `smbclient` directly](https://github.com/nextcloud/server/issues/39063#issuecomment-2002787065).

The intended purpose for this image is as a drop-in replacement for the Nextcloud [Helm Chart](https://github.com/nextcloud/helm).

Our build process [hooks into the upstream repository](.github/workflows/images.yml), so image tags and variants should always be up-to-date.

## Usage

To use the image, simply replace the source of the nextcloud image in your docker-compose/helm chart with either:

- `ghcr.io/spacebird-dev/nextcloud-docker-smb`
- or `quay.io/spacebird-dev/nextcloud-docker-smb`

All versioned upstream tags except for `latest` and the `production` variants should be available.

## Upstream Discussion

Issue [2145](https://github.com/nextcloud/docker/issues/2145) discusses the future of SMB integration into the official Nextcloud Docker image.
If this issue is ever resolved and SMB is included in the base images, this repo may become unnecessary.
