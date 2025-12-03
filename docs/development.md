# Development

## Building the Library from Source

If you need to modify the library or build from source, you must have the Rust toolchain installed.

### Prerequisites

- Rust toolchain (stable 1.91.1)
- `just` CLI tool: https://github.com/casey/just
- `cargo-ndk`: `cargo install cargo-ndk`
- For iOS: CocoaPods >= 1.13: `brew install cocoapods`

### Build Instructions

```shell
# Clone the repo and install prerequisites
git clone git@github.com:bitcoindevkit/bdk-rn.git
cd bdk-rn

# Install compilation targets
rustup target add aarch64-linux-android aarch64-apple-ios aarch64-apple-ios-sim

# Build the library and create tarball (includes both Android and iOS)
just rename-library
just build-tarball  # Builds both platforms and creates bdk-rn-VERSION.tgz

# Install in the example app
cd example
npm install
# The package.json already references the tarball from the parent directory

# For iOS, also install pods
cd ios && pod install && cd ..

# Start the example app
npm run start     # In terminal 1
npm run android   # In terminal 2 (or npm run ios for iOS)
```

## Development Workflow

1. Make changes to the library code
2. Rebuild the library: `just build-android` or `just build-ios`
3. Package the changes: `npm pack`
4. Test in the example app or IntegrationTestingApp
5. Verify functionality before committing
