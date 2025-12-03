# Getting Started

## Running the Example App (Using Pre-Built Tarball)

The `example/` directory contains a full-featured example wallet app. The easiest way to get started is to download a pre-built tarball from our [GitHub Releases](https://github.com/bitcoindevkit/bdk-rn/releases).

### Prerequisites for iOS

- CocoaPods >= 1.13: `brew install cocoapods`

### Installation Steps

```shell
# Clone the repo
git clone git@github.com:bitcoindevkit/bdk-rn.git
cd bdk-rn

# Download the pre-built tarball from GitHub releases and add it to the root of this repository

# Install dependencies in the example app
cd example
npm install
# Note: The tarball is already referenced in package.json as file:../bdk-rn-VERSION.tgz
# Make sure the version matches.

# For iOS, also install pods
cd ios && pod install && cd ..

# Start the example app
npm run start     # In terminal 1
npm run android   # In terminal 2 (or npm run ios for iOS)
```

## Quick Start

1. Download a pre-built tarball from [GitHub Releases](https://github.com/bitcoindevkit/bdk-rn/releases)
2. Add it to your React Native project: `npm install path/to/bdk-rn-VERSION.tgz`
3. For iOS projects, run `cd ios && pod install`
4. Start building your Bitcoin wallet!
