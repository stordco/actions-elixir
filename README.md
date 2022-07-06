# actions-elixir
GitHub Actions for simplifying Elixir operations

# Overview
stordco/actions-elixir implements composite actions for simplifying Elixir
operations - setup, dependency retrieval, etc.

# `stordco/actions-elixir/setup` Action

## Usage
```yaml
  - uses: stordco/actions-elixir/setup@v0.0
    with:
      elixir-version: 1.13.4
      github_personal_access_token: ${{ secrets.GITHUB_PERSONAL_ACCESS_TOKEN }}
      otp-version: 25.0
```

## Inputs
- `cache_path` - (Optional) Override default paths to cache
- `elixir-version` - Specify Elixir version
- `github_personal_access_token` - (Optional) Usually `secrets.GITHUB_PERSONAL_ACCESS_TOKEN`, to setup git for mix dep retrieval
- `otp-version` - Specify OTP version
