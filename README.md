![Codecov](https://img.shields.io/codecov/c/gh/parallaxsecond/rust-tss-esapi)
# TSS 2.0 Enhanced System API Rust Wrapper

> **Fork note.** This is a fork of
> [parallaxsecond/rust-tss-esapi](https://github.com/parallaxsecond/rust-tss-esapi)
> maintained for the [irlume](https://github.com/archledger/irlume) project. The
> `irlume-patches` branch sits on the upstream `tss-esapi-7.7.0` release tag plus
> two patches that irlume needs and that no 7.x release carries:
>
> 1. `Context::policy_authorize_nv` (wraps `TPM2_PolicyAuthorizeNV`), backported
>    from upstream PR #486; irlume calls it for the Tier-2 systemd-pcrlock seal.
> 2. The session-handle flush fix from upstream PR #530, so a failed
>    `tr_sess_set_attributes` inside `execute_with_nullauth_session` (and the two
>    AK helpers `load_ak`/`create_ak_2`) does not leave a loaded session on the TPM.
>
> Both land upstream only in the unreleased 8.0, tracked in upstream issue #495.
> This branch is rebased onto each new stable release and retired once a stable
> `tss-esapi` carries both patches. Fork `main` mirrors upstream `main` for
> reference only. Everything below this note is the upstream README, unchanged.

The `tss-esapi` Rust crate provides an idiomatic interface to the TCG TSS 2.0 Enhanced System API. We expose both direct FFI bindings (under the `tss-esapi-sys` crate) and abstracted versions, aimed at improved convenience of using the API.

## Minimum Supported Rust Version (MSRV)

At the moment we test (via CI) and support the following Rust compiler versions:

* On Ubuntu we test with:
    - The latest stable compiler version, as accessible through `rustup`.
    - The 1.85 compiler version.
* On Fedora we test with the compiler version included with the Fedora 42 release.
* On Fedora rawhide we test with the compiler version included.

If you need support for other versions of the compiler, get in touch with us to see what we can do!

## Community channel

Come and talk to us in [our Slack channel](https://github.com/parallaxsecond/community#community-channel)!

## Contributing

We would be happy for you to contribute to the `tss-esapi` crate!
Please check the [**Contribution Guidelines**](https://parallaxsecond.github.io/parsec-book/contributing/index.html)
to know more about the contribution process.

## License

The software is provided under Apache-2.0. Contributions to this project are accepted under the same license.

*Copyright 2019 Contributors to the Parsec project.*
