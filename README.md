# CI-conf
Workflow YAML files - inspired by https://github.com/jonhoo/rust-ci-conf

# CI.YAML

Build and release wheels using `maturin_action@v1`. Requires adding a PYPI_API_TOKEN to the repository as a repository secret. https://pypi.org/help/#apitoken
Builds every time there is a push or pull request to main, but only releases to PyPI if there is a tag beginning with a _v_.
This file uses a custom manylinux docker image - which has CLANG 14 installed. This is due to mappy-rs using bindgen, which uses CLANG to check the C headers for rust bindings.
To edit the docker image back to normal,To edit the docker image back to normal, edit the container field back to `auto`.

# check.yml

Taken from https://github.com/jonhoo/rust-ci-conf/blob/main/.github/workflows/check.yml. Thanks Jon!
A collection of simple rust checks to make code maintenance easier. Runs on Push or Pull request to main.
In order:
    ```YAML
        fmt - runs cargo fmt to check your RUST code is correctly formatted.
    ```

