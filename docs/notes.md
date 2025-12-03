# Notes and Known Issues

## Known Issues

### 1. cargo-ndk --no-strip Issue

The `cargo-ndk` library removed the `--no-strip` argument and this is creating a build error when using the latest release of `uniffi-bindgen-react-native` (`0.29.3-1`). We are currently building using a commit on their `main` branch which contains the patch. See the `package.json` file for details.

### 2. Emulator Compatibility

For some reason the example app doesn't work on Pixel 8 API 35 emulator, but does work on the Pixel 5 API 31 and the Pixel 9 API 36.

If you get a red banner at the top of the app when launching saying `Unable to load script...` and asking you to start Metro, try the example in a different emulator!

## Troubleshooting

### Metro Bundler Issues

If you encounter Metro bundler issues:

1. Clear the cache: `npm start -- --reset-cache`
2. Try a different emulator version (see compatibility notes above)
3. Make sure Metro is running before launching the app

### Build Issues

If you encounter build issues:

1. Ensure all Rust targets are installed: `rustup target list --installed`
2. Verify `just` is properly installed: `just --version`
3. Check that the bdk-ffi submodule is initialized: `git submodule status`
4. Clean and rebuild: `just clean && just build-tarball`
