<p align="center">
   <img src="media/ci.png" width="355"/>
</p>
<hr/>
<p align="center">
<img src="https://github.com/spectralops/rust-ci-release-template/actions/workflows/build.yml/badge.svg"/>

</p>

# Rust CI Release Template

_A Github Actions based CI release template._


This repo serves as a live template, and reference for building your own CI powered Rust release process on Github Action. This was built to [fill a gap](https://www.reddit.com/r/rust/comments/bjwygr/rust_needs_a_rustreleaser/) that Rust has, and Go doesn't have because Go has [GoReleaser](https://github.com/goreleaser/goreleaser).


Heavily inspired from the [helix](https://github.com/helix-editor/helix) editor project CI workflow + some small tweaks.


**Development**
On each commit, the following is automated:

* CI with caching: check, test, lint

**Release**
Upon pushing a new tag, the following is automated:

* Build for multi-platform binaries: Linux, Windows, macOS
* Create GitHub releases
* Update Homebrew formula

## Quick Start

Just copy `.github/workflows` to your own repo, and set a binary name in your own `Cargo.toml` using a `[[bin]]` block (see the example [Cargo.toml](Cargo.toml)).

Next, check out the point of interest for you to configure / tune below.

## Points of interest


* [Cargo.toml](Cargo.toml) - set your binary name explicitly and take note of it
* [build.yml](.github/workflows/build.yml) - you can use as-is, no parameters to configure
* [release.yml](.github/workflows/release.yml) 
    - Project: at the top of the file, set your own parameters under `env`
    - Project: your binary name should be the same as in your `Cargo.toml`
    - Targets: configure platforms as you wish
    - Homebrew: remove the Homebrew pragma if not needed
    - Homebrew: macOS with ARM chips: customize your formula

# Thanks

To all [Contributors](https://github.com/spectralops/rust-ci-release-template/graphs/contributors) - you make this happen, thanks!


# Copyright

Copyright (c) 2021 [@jondot](http://twitter.com/jondot). See [LICENSE](LICENSE.txt) for further details.

