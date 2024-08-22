# setup

GitHub Composite Action for building and optionally pushing Elixir & Beam based docker containers in an opinionated way.

## Usage

First off, you will want to make sure you have _optimized_ `Dockerfile` and `.dockerignore` files. If you don't, the cache won't do much for you and you'll have a slow build. The biggest areas for this are:
1) Using `.dockerignore` to ignore folders not needed during build (like `.git`). This will speed up copying files, and ensure you don't accidentally add a cache busting file when using wildcards.
2) Use a `Dockerfile` that breaks down steps. This will allow a more efficient use of layers for caching. A good example of this is the default Phoenix `mix phx.gen.release --docker` `Dockerfile`.

Once you have those set up, you can drop this action in. For simple usage, you shouldn't need to specify any settings. By default this will setup Docker layer caching with the GitHub actions cache, set the default image tag based on the repository, and generate recommended image labels like author, repository, and created at time.

<!-- {x-release-please-start-version} -->
```yaml
- name: Build Docker
  uses: stordco/actions-elixir/docker-build@v1.5.1
```
<!-- {x-release-please-end} -->

Most of the time when you build a docker image, you'll want to push it as well. This action _does not_ do any authentication setup, so you'll need to set that up first. Once that is done, just set the `push` value to `true` like so. This will push to `ghcr.io/{{ repository owner }}/{{ repository.name }}`.

<!-- {x-release-please-start-version} -->
```yaml
- name: Build Docker
  uses: stordco/actions-elixir/docker-build@v1.5.1
  with:
    push: true
```
<!-- {x-release-please-end} -->

If you want to change the default image, or even add multiple, you can do so with the `images` value.

<!-- {x-release-please-start-version} -->
```yaml
- name: Build Docker
  uses: stordco/actions-elixir/docker-build@v1.5.1
  with:
    images: |
      ghcr.io/custom-owner/custom-repo
      docker-org/custom-image-name
```
<!-- {x-release-please-end} -->

Lastly, you'll probably want to install some dependencies from our GitHub organization, or our private hex organization. To do so, you can specify the `github-token` and `hex-token` just like the other Elixir actions. This will add the needed build args (for legacy `Dockerfile`s) and secrets (newer updated `Dockerfile`s) to the Docker build

<!-- {x-release-please-start-version} -->
```yaml
- name: Build Docker
  uses: stordco/actions-elixir/docker-build@v1.5.1
  with:
    github-token: ${{ secrets.GH_PERSONAL_ACCESS_TOKEN }}
    hex-token: ${{ secrets.HEX_API_KEY }}
```
<!-- {x-release-please-end} -->

## Inputs

| name | description | default value |
| --- | --- | --- |
| `build-args` | (Optional) A list of extra build args to pass to the build step. Note that the github-token and hex-token will automatically be set if passed in. | |
| `cache` | (Optional) Enables caching built docker layers in the GitHub actions cache. This is highly recommended to speed up builds. Note, if you are not getting a speed bump, check your .dockerignore file to ensure you are not sending files that would break layer caching, like the .git folder. | `true` |
| `context` | (Optional) The build context to use when building the docker image. | `.` |
| `file` | (Optional) The path to the Dockerfile we are building. | `Dockerfile` |
| `github-token` | (Optional) Used to setup mix for pulling private packages from GitHub. This is usually `secrets.GH_PERSONAL_ACCESS_TOKEN`. | `${{ github.token }}` |
| `hex-organization` | (Optional) Hex organization when authenticating. By default this will be the Stord hex organization. | `stord` |
| `hex-token` | (Optional) Used to setup mix for pulling private packages from the hex organization. This is usually `secrets.HEX_API_KEY`. | |
| `images` | (Optional) A list of docker images to use when building and publishing. By default, this will match the repository being built. For example, if you are building `stordco/test-app`, the image will be `ghcr.io/stordco/test-app`. | |
| `labels` | (Optional) A list of labels to be added to the default ones when pushing the image. | |
| `oban-fingerprint` | (Optional) Public key for fetching the oban pro repository data. This is usually refered to as OBAN_KEY_FINTERPRINT in documentation. | |
| `oban-token` | (Optional) Oban pro license key. | |
| `push` | (Optional) Push the final built image to the set registry. | `false` |
| `secrets` | (Optional) A list of extra secrets to pass to the build step. Note that the github-token and hex-token will automatically be set if passed in. | |
| `tags` | (Optional) A list of tags to be added to the default ones when pushing the image. | |

## Outputs

| name | description |
| --- | --- |
| `digest` | The docker build image digest. |
| `image` | The first docker image published. This can be used as reference when deploying the image. |
| `images` | A list of all the published docker images. |
| `labels` | A list of all docker labels used when publishing. |
| `metadata` | The docker build result metadata |
| `tag` | A sha specific tag used when publishing the docker image. This is the most specific tag that won't get repeated and should be used when deploying the image. |
| `tags` | A list of all docker tags that were published. |
