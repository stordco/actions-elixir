# actions-elixir

GitHub Actions for simplifying Stord Elixir operations.

## Setup

GitHub Composite Action for installing Elixir & Beam, setting up and retrieving dependencies along with caching.

### Usage

For basic usage, you don't have to specify anything! Just drop this file in your action and we will pull your elixir and erlang versions from `.tool-versions`, install Elixir, cache your builds and dependencies and run `mix deps.get`.

<!-- {x-release-please-start-version} -->
```yaml
  - name: Setup Elixir
    uses: stordco/actions-elixir/setup@v0.1.2
```
<!-- {x-release-please-end} -->

But some times it's not that simple. If you are using a private package from GitHub or our private Hex organization, you'll need to specify some inputs for those credentials.

<!-- {x-release-please-start-version} -->
```yaml
  - name: Setup Elixir
    uses: stordco/actions-elixir/setup@v0.1.2
    with:
      github_token: ${{ secrets.GH_PERSONAL_ACCESS_TOKEN }}
      hex_token: ${{ secrets.HEX_API_KEY }}
```
<!-- {x-release-please-end} -->

If you are not using [`asdf`](https://asdf-vm.com/) (which you really should be), you can specify the Elixir and Erlang versions with inputs as well.

<!-- {x-release-please-start-version} -->
```yaml
  - name: Setup Elixir
    uses: stordco/actions-elixir/setup@v0.1.2
    with:
      elixir_version: "1.14"
      otp_version: "25.0"
```
<!-- {x-release-please-end} -->

Lastly, if things go wrong and your cache is breaking builds, you can manually increment your cache version. This will ensure no previous cache was used.

<!-- {x-release-please-start-version} -->
```yaml
  - name: Setup Elixir
    uses: stordco/actions-elixir/setup@v0.1.2
    with:
      cache_version: v2
```
<!-- {x-release-please-end} -->

### Inputs

| name | description | default value |
| --- | --- | --- |
| `cache_path` | A list of files, directories, and wildcard patterns to cache and restore. By default this will cache the build and deps folder allowing for faster rebuilding. | `_build deps` |
| `cache_name` | The name of the cache. This is used to build the full cache key. By default this will simply be "cache" but we strongly recommend changing it based on what tool you are using. This is because different tools will have different compile settings, like credo and dialyzer, and therefor have different files cached. | `cache` |
| `cache_version` | (Optional) A version string to include in the cache key. You can change this value to bust the cache if there is an error. | `v1` |
| `elixir_version` | (Optional) Version range or exact version of Elixir to use. If this is not set, we attempt to read the "elixir" field from the .tool-versions file. | |
| `github_token` | (Optional) Used to setup mix for pulling private packages from GitHub. This is usually `secrets.GH_PERSONAL_ACCESS_TOKEN`. | |
| `hex_organization` | (Optional) Hex organization when authenticating. By default this will be the Stord hex organization. | |
| `hex_token` | (Optional) Used to setup mix for pulling private packages from the hex organization. This is usually `secrets.HEX_API_KEY`. | |
| `otp_version` | (Optional) Version range or exact version of Erlang/OTP to use. If this is not set, we attempt to read the "erlang" field from the .tool-versions file. | |

### Outputs

| name | description |
| --- | --- |
| `cache_hit` | A boolean value to indicate an exact match was found for the cache. |
| `elixir_version` | The exact version of Elixir installed. |
| `otp_version` | The exact version of Erlang/OTP installed. |
