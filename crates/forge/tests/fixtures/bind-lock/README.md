# Binding test dependencies

This fixture locks the union of dependencies emitted by `forge bind`. The test workflow checks
it with Socket separately from the workspace lock. Binding tests copy the lock into generated
crates, prune unused direct dependencies, and run Cargo with `--locked`.

When generated dependencies change, update this manifest and lock together. Keep the package
name and version aligned with the `forge bind` defaults. Refresh the lock without compiling:

```sh
cargo generate-lockfile --manifest-path crates/forge/tests/fixtures/bind-lock/Cargo.toml
```
