# Running the Android Example App

You can easily run our example Android application without building the bdk-rn library from source simply by using one of the artifact library tarballs on our release pages.

1. Clone the [bdk-rn-example-apps](https://github.com/UTEXO-Protocol/bdk-rn-example-apps) repository.
2. Download a pre-built tarball from our [GitHub Releases](https://github.com/UTEXO-Protocol/bdk-rn/releases) and put it at the root of the repository.
3. Follow along the next sections to build the Android app and launch it locally.

<div>
  <img src="../../assets/images/android.png" alt="Screenshot 1" style="max-width: 300px;">
</div>

```shell
git clone git@github.com:UTEXO-Protocol/bdk-rn-example-apps.git
cd bdk-rn-example-apps/
# Don't forget to add the tarball at the root of the repo
# https://github.com/UTEXO-Protocol/bdk-rn/releases
npm install
# Start an Android emulator
npm run android
```
