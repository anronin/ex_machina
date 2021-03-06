# Changelog

The noteworthy changes for each ExMachina version are included here. For a
complete changelog, see the git history for each version via the version links.

**To see the dates a version was published see the [hex package page].**

[hex package page]: https://hex.pm/packages/ex_machina

## [1.0.2]

Minor documentation fixes

[1.0.2]: https://github.com/thoughtbot/ex_machina/compare/v1.0.1...v1.0.2

## [1.0.1]

Small change to the error generated when a factory definition is not found ([#142])

[1.0.1]: https://github.com/thoughtbot/ex_machina/compare/v1.0.0...v1.0.1
[#142]: https://github.com/thoughtbot/ex_machina/pull/142

## [1.0.0]

A lot has changed but we tried to make upgrading as simple as possible.

**To upgrade:** In `mix.exs` change the version to `"~> 1.0"` and run `mix
deps.get`. Once you've updated, run `mix test` and ExMachina will raise errors
that show you what needs to change to work with 1.0.0.

### Fixed

- Fix compilation issues under OTP 19 ([#138])
- Raise helpful error when trying to insert twice ([#128])

### Added

- Add `Sequence.next/1` for quickly creating sequences. Example:
  `sequence("username")` will generate `"username1"`, then `"username2"` ([#84])
- Raise if passing invalid keys to structs ([#99])
- Add `params_with_assocs` ([#124])

### Changed

- Rename `fields_for` to `params_for` ([#98])
- If using ExMachina with Ecto, use `insert`, `insert_list` and `insert_pair`
  instead of `create_*`
- Instead of defining a custom `save_record`, you can now implement an
  `ExMachina.Strategy`. See the documentation on hex.pm for more info ([#102])
- Define factory as `user_factory` instead of `factory(:user)` ([#110]). See PR
  and related issue for details on why this was changed.
- `params_for` no longer returns the primary key ([#123])

[1.0.0]: https://github.com/thoughtbot/ex_machina/compare/v0.6.1...v1.0.0
[#138]: https://github.com/thoughtbot/ex_machina/pull/138
[#128]: https://github.com/thoughtbot/ex_machina/pull/128
[#84]: https://github.com/thoughtbot/ex_machina/pull/84
[#99]: https://github.com/thoughtbot/ex_machina/pull/99
[#124]: https://github.com/thoughtbot/ex_machina/pull/124
[#98]: https://github.com/thoughtbot/ex_machina/pull/98
[#102]: https://github.com/thoughtbot/ex_machina/pull/102
[#110]: https://github.com/thoughtbot/ex_machina/pull/110
[#123]: https://github.com/thoughtbot/ex_machina/pull/123

## [0.6.1]

Removes warnings as reported by
https://github.com/thoughtbot/ex_machina/issues/70. We recommend updating if you
are using Ecto 1.1. There are no backward incompatible changes and no new
features.

[0.6.1]: https://github.com/thoughtbot/ex_machina/compare/v0.6.0...v0.6.1

## [0.6.0]

You can continue using ExMachina 0.5.0 if you are not ready for Ecto 1.1 yet.
There are no additional new features in this release.

- Updated to use Ecto 1.1
- Require Ecto 1.1

There are still some warnings that we need to fix for Ecto 1.1, but this release
at least fixes the error that was caused when upgrading to Ecto 1.1.

[0.6.0]: https://github.com/thoughtbot/ex_machina/compare/v0.5.0...v0.6.0

## [0.5.0]

### Changed

- Factories were simplified so that `attrs` is no longer required. See [70a0481] and [issue #56]
- ExMachina.Ecto.assoc/3 was removed. You can now use build(:factory) instead. See discussion in [issue #56]

### Fixed
- Use association id as defined on the schema [7c67047]

[issue #56]:https://github.com/thoughtbot/ex_machina/issues/56
[70a0481]: https://github.com/thoughtbot/ex_machina/commit/70a04814aacc33b3c727e133f4bd6b03a8217731
[7c67047]:https://github.com/thoughtbot/ex_machina/commit/7c6704706cffa7285a608049a1b1f10784790fdd
[0.5.0]: https://github.com/thoughtbot/ex_machina/compare/v0.4.0...v0.5.0

## [0.4.0]

### Added

- Add support for `has_many` and `has_one` Ecto associations. See [1ff4198].

### Changed

- Factories must now be defined with functions. See [59b7d23]

[1ff4198]: https://github.com/thoughtbot/ex_machina/commit/1ff4198488caa8225563ec2d4262a6f42d7d29be
[59b7d23]: https://github.com/thoughtbot/ex_machina/commit/59b7d23522d8ef4a3ae209f856b4d3c159de376e
[0.4.0]: https://github.com/thoughtbot/ex_machina/compare/v0.3.0...v0.4.0

## [0.3.0]

### Added

- Add `build_list` and `build_pair`. See [8f332ce].
- Add a `create` method that takes a map. This allows you to chain functions
like: `build(:foo) |> make_admin |> create`. See [59cbef5].

[8f332ce]: https://github.com/thoughtbot/ex_machina/commit/8f332ce0499f4e81f9dbb653fef3a6bc1e697cb6
[59cbef5]: https://github.com/thoughtbot/ex_machina/commit/59cbef569d7740d2958653fe177790b0cb506ff6

### Changed

- Factories must now be defined with a macro. See [03c41f6]
- `belongs_to` associations are now built instead of created. See [b518285].

[b518285]: https://github.com/thoughtbot/ex_machina/commit/b518285fa144459c36848bda5e72498914c19cdd
[03c41f6]: https://github.com/thoughtbot/ex_machina/commit/03c41f64470423a168f91d40edcd91eb242c3c61
[0.3.0]: https://github.com/thoughtbot/ex_machina/compare/v0.2.0...v0.3.0

## [0.2.0]

### Changed

- Ecto functionality was extracted to `ExMachina.Ecto`. See [270c19b].

[270c19b]: https://github.com/thoughtbot/ex_machina/commit/270c19bbb805b7c62365612419410990f28c8baf
[0.2.0]: https://github.com/thoughtbot/ex_machina/compare/v0.1.0...v0.2.0
