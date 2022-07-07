# actions-elixir
GitHub Actions for simplifying Elixir operations

# Overview
stordco/actions-elixir implements composite actions for simplifying Elixir
operations - setup, dependency retrieval, etc.

# `stordco/actions-elixir/setup` Action

## Usage
```yaml
  - uses: stordco/actions-elixir/setup@v0.1
    with:
      elixir_version: 1.13.4
      github_personal_access_token: ${{ secrets.GITHUB_PERSONAL_ACCESS_TOKEN }}
      otp_version: 25.0
```

## Inputs
- `cache_path` - (Optional) Override default paths to cache
- `elixir_version` - Specify Elixir version
- `github_personal_access_token` - (Optional) Usually `secrets.GITHUB_PERSONAL_ACCESS_TOKEN`, to setup git for mix dep retrieval
- `otp_version` - Specify OTP version
