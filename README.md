# `gctx` - A `gcloud` configuration utility

Manage [Google Cloud Platform](https://cloud.google.com/) `gcloud` configurations easily and quickly

## Motivation

I'm often working with multiple GCP projects with a variety of different settings (e.g. default compute zone).
To do this, I take advantage of the [`gcloud config configurations`](https://cloud.google.com/sdk/gcloud/reference/config/configurations)
command in the standard `gcloud` tooling. However, this has two major problems:

- It's quite a lot of typing if you're switching often. Sure, an alias can help, but...
- `gcloud` is slow to initialise which makes it annoying to use and to add to your default prompt

After having used [`kubectx`](https://github.com/ahmetb/kubectx) to solve a similar problem switching between
Kubernetes contexts easily, I searched for a similar tool that could easily switch between `gcloud` configurations
but couldn't find anything. So, having spent a while learning [Rust](https://www.rust-lang.org/) and being incredibly
impressed, I thought it would make a great starter project.

## Goals

`gctx` aims to achieve similar goals to `kubectx`, such as:

- Extremely fast switching between different `gcloud` configurations
- Cross platform
- Shorter to type than `gcloud config configurations activate` 😄
- **TBD:** Fuzzy finding using `fzf` (if installed)

## Installation

### Using `cargo`

Get the latest stable version of Rust via [`rustup`](https://rustup.rs/) and run:

```bash
cargo install gctx
```

**TODO**: Pre-build binaries with support for common CLI installers such as `brew` and `scoop`

## Usage

**Note:** Usage is currently entirely TBD

```bash
# show the current configuration (useful for adding to default prompt)
gctx current
# or shorthand, just omit current
gctx

# list all configurations
gctx list

# activate a different configuration
gctx my-config
# or to explicitly activate, e.g. if your configuration name clashes with a gctx command
gctx activate my-config

# show the properties of a configuration (like gcloud config configurations describe)
# defaults to the current configuration
gctx describe
gctx describe other-name

# rename a configuration
gctx rename old-name new-name

# use force to overwrite an existing configuration
gctx rename --force old-name existing-name

# show help and usage
gctx --help
```
