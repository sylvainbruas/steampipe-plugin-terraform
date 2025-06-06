## v1.1.1 [2025-04-18]

_Bug fixes_

- Fixed Linux AMD64 plugin build failures for `Postgres 14 FDW`, `Postgres 15 FDW`, and `SQLite Extension` by upgrading GitHub Actions runners from `ubuntu-20.04` to `ubuntu-22.04`.

## v1.1.0 [2025-04-17]

_Dependencies_

- Recompiled plugin with Go version `1.23.1`. ([#125](https://github.com/turbot/steampipe-plugin-terraform/pull/125))
- Recompiled plugin with [steampipe-plugin-sdk v5.11.5](https://github.com/turbot/steampipe-plugin-sdk/blob/v5.11.5/CHANGELOG.md#v5115-2025-03-31) that addresses critical and high vulnerabilities in dependent packages. ([#125](https://github.com/turbot/steampipe-plugin-terraform/pull/125))

## v1.0.1 [2025-02-12]

_Bug fixes_

- Fixed the `terraform_resource` table to correctly return data instead of `index out of range` error when the `state_file_paths` config argument is set in the `terraform.spc` file. ([#109](https://github.com/turbot/steampipe-plugin-terraform/pull/109))

## v1.0.0 [2024-10-22]

There are no significant changes in this plugin version; it has been released to align with [Steampipe's v1.0.0](https://steampipe.io/changelog/steampipe-cli-v1-0-0) release. This plugin adheres to [semantic versioning](https://semver.org/#semantic-versioning-specification-semver), ensuring backward compatibility within each major version.

_Dependencies_

- Recompiled plugin with Go version `1.22`. ([#107](https://github.com/turbot/steampipe-plugin-terraform/pull/107))
- Recompiled plugin with [steampipe-plugin-sdk v5.10.4](https://github.com/turbot/steampipe-plugin-sdk/blob/develop/CHANGELOG.md#v5104-2024-08-29) that fixes logging in the plugin export tool. ([#107](https://github.com/turbot/steampipe-plugin-terraform/pull/107))

## v0.12.0 [2024-06-21]

_What's new?_

- New tables added
  - [terraform_variable](https://hub.steampipe.io/plugins/turbot/terraform/tables/terraform_variable) ([#97](https://github.com/turbot/steampipe-plugin-terraform/pull/97))

_Enhancements_

- The Plugin and the Steampipe Anywhere binaries are now built with the `netgo` package. ([#101](https://github.com/turbot/steampipe-plugin-terraform/pull/101))
- Added the `version` flag to the plugin's Export tool. ([#65](https://github.com/turbot/steampipe-export/pull/65))

_Bug fixes_

- Fixed the `arguments` column of `terraform_resource` table to correctly return the `type` field. ([#99](https://github.com/turbot/steampipe-plugin-terraform/pull/99)) ([#92](https://github.com/turbot/steampipe-plugin-terraform/pull/92))

_Dependencies_

- Recompiled plugin with [steampipe-plugin-sdk v5.10.1](https://github.com/turbot/steampipe-plugin-sdk/blob/main/CHANGELOG.md#v5100-2024-04-10) that adds support for connection key columns. ([#92](https://github.com/turbot/steampipe-plugin-terraform/pull/92))

## v0.11.2 [2023-12-12]

_Bug fixes_

- Fix the missing optional tag on the plugin's connection config arguments. [#84](https://github.com/turbot/steampipe-plugin-terraform/pull/84)

## v0.11.1 [2023-12-12]

_Bug fixes_

- Fixed the plugin's connection config variables to use the `hcl` syntax. ([#82](https://github.com/turbot/steampipe-plugin-terraform/pull/82))

## v0.11.0 [2023-12-12]

_What's new?_

- The plugin can now be downloaded and used with the [Steampipe CLI](https://steampipe.io/docs), as a [Postgres FDW](https://steampipe.io/docs/steampipe_postgres/overview), as a [SQLite extension](https://steampipe.io/docs//steampipe_sqlite/overview) and as a standalone [exporter](https://steampipe.io/docs/steampipe_export/overview). ([#80](https://github.com/turbot/steampipe-plugin-terraform/pull/80))
- The table docs have been updated to provide corresponding example queries for Postgres FDW and SQLite extension. ([#80](https://github.com/turbot/steampipe-plugin-terraform/pull/80))
- Docs license updated to match Steampipe [CC BY-NC-ND license](https://github.com/turbot/steampipe-plugin-terraform/blob/main/docs/LICENSE). ([#80](https://github.com/turbot/steampipe-plugin-terraform/pull/80))

_Dependencies_

- Recompiled plugin with [steampipe-plugin-sdk v5.8.0](https://github.com/turbot/steampipe-plugin-sdk/blob/main/CHANGELOG.md#v580-2023-12-11) that includes plugin server encapsulation for in-process and GRPC usage, adding Steampipe Plugin SDK version to `_ctx` column, and fixing connection and potential divide-by-zero bugs. ([#79](https://github.com/turbot/steampipe-plugin-terraform/pull/79))

## v0.10.0 [2023-10-03]

_Breaking changes_

- Removed `instances` column from `terraform_resource` table. ([#64](https://github.com/turbot/steampipe-plugin-terraform/pull/64))
- All `arguments` and `lifecycle` columns now return `null` instead of `{}` if empty.  ([#64](https://github.com/turbot/steampipe-plugin-terraform/pull/64))

_Enhancements_

- Added `address`, `attributes`, and `attributes_std` columns to `terraform_resource` table. ([#64](https://github.com/turbot/steampipe-plugin-terraform/pull/64))

_Bug fixes_

- Fixed the `start_line`, `end_line` and `source` column values in the `terraform_resource` table to return correct values regardless of file indentation. ([#64](https://github.com/turbot/steampipe-plugin-terraform/pull/64))
- Fixed the plugin to check all files even if a non-existent file name is provided in any `file_paths` config arg. ([#67](https://github.com/turbot/steampipe-plugin-terraform/pull/67))

_Dependencies_

- Recompiled plugin with [steampipe-plugin-sdk v5.6.2](https://github.com/turbot/steampipe-plugin-sdk/blob/main/CHANGELOG.md#v562-2023-10-03) which prevents nil pointer reference errors for implicit hydrate configs. ([#63](https://github.com/turbot/steampipe-plugin-terraform/pull/63))

## v0.9.0 [2023-10-02]

_Dependencies_

- Upgraded to [steampipe-plugin-sdk v5.6.1](https://github.com/turbot/steampipe-plugin-sdk/blob/main/CHANGELOG.md#v561-2023-09-29) with support for rate limiters. ([#63](https://github.com/turbot/steampipe-plugin-terraform/pull/63))
- Recompiled plugin with Go version `1.21`. ([#63](https://github.com/turbot/steampipe-plugin-terraform/pull/63))

## v0.8.1 [2023-09-15]

_Bug fixes_

- Fixed the `invalid memory address or nil pointer dereference` errors when querying Terraform configuration or plan or state files that included `null` valued arguments. ([#56](https://github.com/turbot/steampipe-plugin-terraform/pull/56))

_Dependencies_

- Recompiled plugin with [steampipe-plugin-sdk v5.5.1](https://github.com/turbot/steampipe-plugin-sdk/blob/main/CHANGELOG.md#v551-2023-07-26). ([#49](https://github.com/turbot/steampipe-plugin-terraform/pull/49))
- Recompiled plugin with `github.com/turbot/go-kit v0.7.0`. ([#52](https://github.com/turbot/steampipe-plugin-terraform/pull/52))

## v0.8.0 [2023-09-07]

_What's new?_

- Added support to parse Terraform plan and state files. This can be set using the `plan_file_paths` and `state_file_paths` config arguments in the `terraform.spc` file. ([#40](https://github.com/turbot/steampipe-plugin-terraform/pull/40))

_Deprecated_

- The `paths` argument in the `terraform.spc` file has been deprecated and replaced with the `configuration_file_paths` argument. ([#40](https://github.com/turbot/steampipe-plugin-terraform/pull/40))

## v0.7.0 [2023-06-20]

_Dependencies_

- Recompiled plugin with [steampipe-plugin-sdk v5.5.0](https://github.com/turbot/steampipe-plugin-sdk/blob/v5.5.0/CHANGELOG.md#v550-2023-06-16) which significantly reduces API calls and boosts query performance, resulting in faster data retrieval. This update significantly lowers the plugin initialization time of dynamic plugins by avoiding recursing into child folders when not necessary. ([#41](https://github.com/turbot/steampipe-plugin-terraform/pull/41))

## v0.6.0 [2023-06-07]

_Bug fixes_

- Fixed the `arguments` column of `terraform_module` table to correctly return data instead of `null`. ([#36](https://github.com/turbot/steampipe-plugin-terraform/pull/36)) (Thanks [@rollwagen](https://github.com/rollwagen) for the contribution!!)

_Dependencies_

- Recompiled plugin with [steampipe-plugin-sdk v5.4.1](https://github.com/turbot/steampipe-plugin-sdk/blob/main/CHANGELOG.md#v541-2023-05-05) which fixes increased plugin initialization time due to multiple connections causing the schema to be loaded repeatedly. ([#38](https://github.com/turbot/steampipe-plugin-terraform/pull/38))

## v0.5.0 [2023-04-11]

_Dependencies_

- Recompiled plugin with [steampipe-plugin-sdk v5.3.0](https://github.com/turbot/steampipe-plugin-sdk/blob/main/CHANGELOG.md#v530-2023-03-16) which includes fixes for query cache pending item mechanism and aggregator connections not working for dynamic tables. ([#33](https://github.com/turbot/steampipe-plugin-terraform/pull/33))

## v0.4.0 [2023-02-16]

_What's new?_

- New tables added
  - [terraform_module](https://hub.steampipe.io/plugins/turbot/terraform/tables/terraform_module) ([#28](https://github.com/turbot/steampipe-plugin-terraform/pull/28)) (Thanks [@rollwagen](https://github.com/rollwagen) for the contribution!!)

## v0.3.0 [2022-11-16]

_What's new?_

- Added support for retrieving Terraform configuration files from remote Git repositories and S3 buckets. For more information, please see [Supported Path Formats](https://hub.steampipe.io/plugins/turbot/terraform#supported-path-formats). ([#25](https://github.com/turbot/steampipe-plugin-terraform/pull/25))
- Added file watching support for files included in the `paths` config argument. ([#25](https://github.com/turbot/steampipe-plugin-terraform/pull/25))

_Enhancements_

- Added `end_line` and `source` columns to all tables. ([#25](https://github.com/turbot/steampipe-plugin-terraform/pull/25))

_Dependencies_

- Recompiled plugin with [steampipe-plugin-sdk v5.0.0](https://github.com/turbot/steampipe-plugin-sdk/blob/main/CHANGELOG.md#v500-2022-11-16) which includes support for fetching remote files with go-getter and file watching. ([#25](https://github.com/turbot/steampipe-plugin-terraform/pull/25))

## v0.2.0 [2022-09-09]

_Dependencies_

- Recompiled plugin with [steampipe-plugin-sdk v4.1.6](https://github.com/turbot/steampipe-plugin-sdk/blob/main/CHANGELOG.md#v416-2022-09-02) which includes several caching and memory management improvements. ([#21](https://github.com/turbot/steampipe-plugin-terraform/pull/21))
- Recompiled plugin with Go version `1.19`. ([#21](https://github.com/turbot/steampipe-plugin-terraform/pull/21))

## v0.1.0 [2022-04-28]

_Enhancements_

- Added support for native Linux ARM and Mac M1 builds. ([#17](https://github.com/turbot/steampipe-plugin-terraform/pull/17))
- Recompiled plugin with [steampipe-plugin-sdk v3.1.0](https://github.com/turbot/steampipe-plugin-sdk/blob/main/CHANGELOG.md#v310--2022-03-30) and Go version `1.18`. ([#16](https://github.com/turbot/steampipe-plugin-terraform/pull/16))

## v0.0.5 [2022-02-10]

_What's new?_

- File loading and matching through the `paths` argument has been updated to make the plugin easier to use:
  - The `paths` argument is no longer commented out by default for new plugin installations and now defaults to the current working directory
  - Home directory expansion (`~`) is now supported
  - Recursive directory searching (`**`) is now supported
- Previously, when using wildcard matching (`*`), non-Terraform configuration files were automatically excluded to prevent parsing errors. These files are no longer automatically excluded to allow for a wider range of matches. If your current configuration uses wildcard matching, e.g., `paths = [ "/path/to/my/files/*" ]`, please update it to include the file extension, e.g., `paths = [ "/path/to/my/files/*.tf" ]`.

## v0.0.4 [2022-02-01]

_Bug fixes_

- Fixed: Add lock to file parsing function to prevent concurrent map read/write errors ([#9](https://github.com/turbot/steampipe-plugin-terraform/pull/9))

## v0.0.3 [2022-01-14]

_Enhancements_

- Recompiled plugin with [steampipe-plugin-sdk v1.8.3](https://github.com/turbot/steampipe-plugin-sdk/blob/main/CHANGELOG.md#v183--2021-12-23)

_Bug fixes_

- Fixed `terraform_local` queries intermittently failing due to a value conversion error

## v0.0.2 [2021-12-16]

_Enhancements_

- Recompiled plugin with Go version 1.17 ([#4](https://github.com/turbot/steampipe-plugin-terraform/pull/4))

## v0.0.1 [2021-12-02]

_What's new?_

- New tables added

  - [terraform_data_source](https://hub.steampipe.io/plugins/turbot/terraform/tables/terraform_data_source)
  - [terraform_local](https://hub.steampipe.io/plugins/turbot/terraform/tables/terraform_local)
  - [terraform_output](https://hub.steampipe.io/plugins/turbot/terraform/tables/terraform_output)
  - [terraform_provider](https://hub.steampipe.io/plugins/turbot/terraform/tables/terraform_provider)
  - [terraform_resource](https://hub.steampipe.io/plugins/turbot/terraform/tables/terraform_resource)
