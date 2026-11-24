# navree-swift

The Apple client of [Navree](https://github.com/NavreeHQ/navree), for iPhone, iPad and Mac, as a Swift package. Each release of Navree fills this repository: its workflow (`.github/workflows/update.yml`) commits the package of that release and tags it with the version, without a `v` (`1.5.0`). There is no package here until the first release that makes one.

The client's source, documentation and tests are in [`packages/apple`](https://github.com/NavreeHQ/navree/tree/main/packages/apple) of Navree. `navree native:init` writes an Apple client project that uses this package.
