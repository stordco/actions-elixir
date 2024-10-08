# Changelog

## [1.5.1](https://github.com/stordco/actions-elixir/compare/v1.5.0...v1.5.1) (2024-08-22)


### Bug Fixes

* remove cache restore key causing incorrect restore files ([#46](https://github.com/stordco/actions-elixir/issues/46)) ([0590eca](https://github.com/stordco/actions-elixir/commit/0590eca9c479112d9a29b22352910db160ebfe6e))

## [1.5.0](https://github.com/stordco/actions-elixir/compare/v1.4.1...v1.5.0) (2024-08-21)


### Features

* setup hexpm mirror and timeout for better reliability ([#44](https://github.com/stordco/actions-elixir/issues/44)) ([9b7f28a](https://github.com/stordco/actions-elixir/commit/9b7f28a0a943fefbd36732be1141f9e73c6b4dbf))

## [1.4.1](https://github.com/stordco/actions-elixir/compare/v1.4.0...v1.4.1) (2024-02-20)


### Bug Fixes

* add shell to dep clean ([ceef4c5](https://github.com/stordco/actions-elixir/commit/ceef4c5e8c53601e7665de9ab95ac230010af967))

## [1.4.0](https://github.com/stordco/actions-elixir/compare/v1.3.0...v1.4.0) (2024-02-20)


### Features

* clean dependencies on reruns ([#31](https://github.com/stordco/actions-elixir/issues/31)) ([2b68339](https://github.com/stordco/actions-elixir/commit/2b6833955d256c29a74692342decc7a9ed3432ea))
* remove tool versions action with new native setup-beam feature ([#37](https://github.com/stordco/actions-elixir/issues/37)) ([ba2cddb](https://github.com/stordco/actions-elixir/commit/ba2cddbe478a8f7692e5b38d2c3deb9a6b9055b4))


### Bug Fixes

* update release please configuration ([#39](https://github.com/stordco/actions-elixir/issues/39)) ([25975e5](https://github.com/stordco/actions-elixir/commit/25975e5902c1712d21219ae130531f563ebb0738))

## [1.3.0](https://github.com/stordco/actions-elixir/compare/v1.2.3...v1.3.0) (2023-08-28)


### Features

* support passing platforms to docker build ([#26](https://github.com/stordco/actions-elixir/issues/26)) ([1b773fc](https://github.com/stordco/actions-elixir/commit/1b773fca39749682041cd1afbcb8e47dfe341f28))

## [1.2.3](https://github.com/stordco/actions-elixir/compare/v1.2.2...v1.2.3) (2022-11-30)


### Bug Fixes

* update dependencies and remove deprecation message ([6a5d111](https://github.com/stordco/actions-elixir/commit/6a5d111875a4625d7fa92d8da1e9ec8dbc87cb08))

## [1.2.1](https://github.com/stordco/actions-elixir/compare/v1.2.0...v1.2.1) (2022-09-15)


### Bug Fixes

* update setup action with oban new line issues ([#18](https://github.com/stordco/actions-elixir/issues/18)) ([3d9abed](https://github.com/stordco/actions-elixir/commit/3d9abed6cfc9f720b7e480752223e6c57b795c28))

## [1.2.0](https://github.com/stordco/actions-elixir/compare/v1.1.0...v1.2.0) (2022-09-15)


### Features

* allow adding oban pro repository ([#16](https://github.com/stordco/actions-elixir/issues/16)) ([36fc307](https://github.com/stordco/actions-elixir/commit/36fc307f3b2af9981b853597c99575a982183563))

## [1.1.0](https://github.com/stordco/actions-elixir/compare/v1.0.2...v1.1.0) (2022-09-14)


### Features

* create a docker-build action ([#13](https://github.com/stordco/actions-elixir/issues/13)) ([d9dcad7](https://github.com/stordco/actions-elixir/commit/d9dcad7717fc32542aeaf29a5cc89d6144656514))


### Bug Fixes

* update release to update new README files ([#15](https://github.com/stordco/actions-elixir/issues/15)) ([d9df027](https://github.com/stordco/actions-elixir/commit/d9df027b6716010866c354566be0b7ea7452f773))

## [1.0.2](https://github.com/stordco/actions-elixir/compare/v1.0.1...v1.0.2) (2022-09-09)


### Bug Fixes

* checkout correct release on new release publishing ([942367d](https://github.com/stordco/actions-elixir/commit/942367d837aa1dabbebf90e1f7d4d41f3b7b04a1))

## [1.0.1](https://github.com/stordco/actions-elixir/compare/v1.0.0...v1.0.1) (2022-09-09)


### Bug Fixes

* update release workflow ([0b785de](https://github.com/stordco/actions-elixir/commit/0b785de68dd00e704fa75b4df88a8bbf41d97222))

## [1.0.0](https://github.com/stordco/actions-elixir/compare/v0.1.2...v1.0.0) (2022-09-09)


### ⚠ BREAKING CHANGES

* use hyphens over underscores for inputs and outputs
* add support for private hex repository (#6)

### Features

* add support for private hex repository ([#6](https://github.com/stordco/actions-elixir/issues/6)) ([f6dd6ac](https://github.com/stordco/actions-elixir/commit/f6dd6ac2f3e602c9c0ec6450618a8b34ceaa43d8))
* setup release automation and proper git tags ([#5](https://github.com/stordco/actions-elixir/issues/5)) ([8d1a20a](https://github.com/stordco/actions-elixir/commit/8d1a20a8eeb06e55b0a84d4604852ceed7a62773))
* use job name as cache title by default ([5d52701](https://github.com/stordco/actions-elixir/commit/5d52701675c3719907ed5bfb9053ce6de605e320))


### Bug Fixes

* unset optional input values ([b5344fd](https://github.com/stordco/actions-elixir/commit/b5344fd8745eb37f7c04f5cfc164eb14ea0d04af))
* update release-please manifest version ([#8](https://github.com/stordco/actions-elixir/issues/8)) ([e57f320](https://github.com/stordco/actions-elixir/commit/e57f3205c005fd66960bce056f4c2c1d9afb5e63))
* use .tool-versions erlang version not otp ([a046ca0](https://github.com/stordco/actions-elixir/commit/a046ca0cf60d62f5fc553f75fdea89a17851b072))


### Miscellaneous Chores

* use hyphens over underscores for inputs and outputs ([11bdcef](https://github.com/stordco/actions-elixir/commit/11bdcef44b9f2858390eb9cb961bf472d54e45d8))
