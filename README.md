# Navree Native for Apple platforms

The Apple client of [Navree](https://github.com/NavreeHQ/navree) 1.5.0, as a Swift package: an app for iPhone, iPad and Mac (iOS 26, iPadOS 26 and macOS 26 or later) whose screens a Navree server draws, natively. This repository is made by each release of Navree; change the client in [`packages/apple`](https://github.com/NavreeHQ/navree/tree/v1.5.0/packages/apple), where its documentation, tests and demo app are.

## Adding it

A new project: `navree native:init` in a Navree app writes one that uses this package.

An existing project: in Xcode, File > Add Package Dependencies, `https://github.com/NavreeHQ/navree-swift`, Up to Next Minor Version from 1.5.0, and the product `NavreeNative`. In a `Package.swift`:

```swift
.package(url: "https://github.com/NavreeHQ/navree-swift", .upToNextMinor(from: "1.5.0"))
```

Then `import NavreeShell`, make a `ShellConfiguration` with the server's origin, and show `NavreeScenes(configuration:)`. Keep the package at the minor version of Navree the server runs: what a native client is answered may change in a minor release.

The runtime core is a prebuilt binary (`NavreeCore.xcframework`, downloaded from the Navree release and checked by its SHA-256) for Apple silicon only: an iPhone or iPad, the iOS simulator on an Apple silicon Mac, and an Apple silicon Mac. A Mac app sets `ARCHS = arm64`, and a simulator build leaves out `x86_64` (`EXCLUDED_ARCHS[sdk=iphonesimulator*] = x86_64`).

## Licence

MIT or Apache 2.0, at your option, as Navree.
