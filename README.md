# actions-elixir

GitHub Actions for simplifying Elixir operations

## Overview

stordco/actions-elixir implements composite actions for simplifying Elixir
operations - setup, dependency retrieval, etc.

## `stordco/actions-elixir/setup` Action

### Usage

<!-- {x-release-please-start-version} -->
```yaml
  - uses: stordco/actions-elixir/setup@v0.1
    with:
      elixir_version: "1.13"
      github_token: ${{ secrets.GH_PERSONAL_ACCESS_TOKEN }}
      otp_version: "25.0"
```
<!-- {x-release-please-end} -->

### Inputs

- `cache_path` - (Optional) Override default paths to cache
- `elixir_version` - Specify Elixir version
- `github_token` - (Optional) Usually `secrets.GH_PERSONAL_ACCESS_TOKEN`, to setup git for mix dep retrieval
- `otp_version` - Specify OTP version
