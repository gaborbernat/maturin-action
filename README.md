# maturin-action

[![GitHub Actions](https://github.com/messense/maturin-action/actions/workflows/test.yml/badge.svg)](https://github.com/messense/maturin-action/actions?query=workflow%3ATest)

GitHub Action to install and run a custom [maturin](https://github.com/PyO3/maturin) command

## Usage

```yaml
- uses: actions-rs/toolchain@v1
  with:
    profile: minimal
    toolchain: stable
    override: true
- uses: messense/maturin-action@v1
  with:
    maturin-version: latest
    command: build
    args: --release
```

### Examples

* [messense/crfs-rs](https://github.com/messense/crfs-rs/blob/main/.github/workflows/Python.yml)

## Inputs

### `command`

**Optional** `maturin` command to run. Defaults to `build`.

### `args`

**Optional** Arguments to pass to the `maturin` command.

### `maturin-version`

**Optional** The version of `maturin` to use. Must match a tagged release. Defaults to `latest`.

See: https://github.com/PyO3/maturin/releases

### `manylinux`

**Optional** Control the manylinux platform tag on linux, ignored on other platforms.
Only passed to maturin `build` and `publish` commands.

### `target`

**Optional** The `--target` option for Cargo. Only passed to maturin `build` and `publish` commands.

### `container`

**Optional** manylinux docker container image name, Default depends on `target` and `manylinux` options.
Set to `off` to disable manylinux docker build and build on the host instead.

### `rust-toolchain`

**Optional** Rust toolchain name. Defaults to `stable` for Docker build.

## License

This work is released under the MIT license. A copy of the license is provided in the [LICENSE](./LICENSE) file.
