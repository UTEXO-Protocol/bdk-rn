# Testing

## Running the IntegrationTestingApp

The `IntegrationTestingApp/` directory contains a standalone test app that uses the library as a tarball dependency (similar to how end-users would consume it). This app is **not** part of the workspace and is completely decoupled from the library development.

You can use the following workflow to run the tests locally on an Android emulator, or to develop features on the library by first making changes to the local `bdk-ffi` repository, and then running through the workflow with new/modified tests.

### Running Integration Tests

```shell
# First, build and package the library
just build-android
npm pack  # Creates bdk-rn-0.1.0.tgz

# Install dependencies in the IntegrationTestingApp
cd IntegrationTestingApp
npm install
npm install ../bdk-rn-0.1.0-next.tgz

# To see tests results in your shell, run this prior to starting the app
adb logcat -c && adb logcat -s ReactNativeJS | tee tests.log

# Run the app
npm run android  # or npm run ios
```

## Test Development Workflow

1. Make changes to `bdk-ffi` or the library code
2. Build and package: `just build-android && npm pack`
3. Update IntegrationTestingApp: `cd IntegrationTestingApp && npm install ../bdk-rn-VERSION.tgz`
4. Add or modify tests in the IntegrationTestingApp
5. Run the app and verify test results in logcat
