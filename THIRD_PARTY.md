# Third-party components and source

The install-only Manager permission does **not** apply to the independently licensed components below. Their own licenses and modification/distribution rights remain in force.

| Component in the SPK | Source snapshot | License |
|---|---|---|
| `payload/bin/wg` (wireguard-tools) | `third_party/source/wireguard-tools-a998407.tar`, upstream revision `a998407747005ea7e4e0258d96f105c97241e1d3` | GPL-2.0; full text in `third_party/licenses/wireguard-tools-GPL-2.0.txt` |
| `payload/bin/wireguard-go` | `third_party/source/wireguard-go-ecfc5a8.tar`, upstream revision `ecfc5a8d54462e18e13c72173e2623d16d8e25a0` | MIT; notice in `third_party/licenses/wireguard-go-MIT.txt` |
| Go modules linked into `wireguard-go` | `golang.org/x/crypto` v0.37.0, `x/net` v0.39.0, `x/sys` v0.32.0 | BSD-3-Clause notices in `third_party/licenses/` |
| glibc linked into `wg` | `third_party/source/glibc-3aae843.tar.gz`, revision `3aae843e9e9e6a2502e98ff44d2671b20a023f8e` | LGPL-2.1; full text in `third_party/licenses/COPYING.LIB` |

All listed paths are **inside the SPK's `package.tgz`**. The package also contains 12 relinkable `wg` object files in `third_party/relinkable/wg-objects/`. They are supplied so recipients can relink the statically linked program with a modified LGPL library. The source snapshots and notices are distributed with the installer; they are not subject to the Manager-specific no-derivatives condition.

The build uses an Arm GNU Toolchain 12.2 glibc-based static link for Linux ARMv7. Arm's [12.2 release notes](https://documentation-service.arm.com/static/66617d9c8ee2517dbbc3bebf) identify the glibc revision above. The corresponding upstream projects are [wireguard-tools](https://git.zx2c4.com/wireguard-tools), [wireguard-go](https://git.zx2c4.com/wireguard-go), and [glibc](https://sourceware.org/git/?p=glibc.git).

SHA-256 values of the bundled binaries and source archives:

| SPK path | SHA-256 |
|---|---|
| `payload/bin/wg` | `73650a73918476e261bac1e0225644c99d1d64af52d20cff9c707c78a48645a7` |
| `payload/bin/wireguard-go` | `e29051ab5ba6dfa0fe1021f757dfa7145da7ebe6cc1248e1dc84f6b806038a0e` |
| `third_party/source/wireguard-tools-a998407.tar` | `89ee8fd65131a89c87102bf849131b97df961f74c85e3302f5ead528e5c38328` |
| `third_party/source/wireguard-go-ecfc5a8.tar` | `ce435baf9760316910faecfee4b28ad848e0c4c90c6de227d21cd35b44cf0fa9` |
| `third_party/source/glibc-3aae843.tar.gz` | `3f61d8c3aa5a3590372f1ced060fc2f4829281753e77ce596939002ae383de67` |

The package was built with the LGPL source and object materials above, but this release has **not** received an independent license-compliance review. The [GNU GPL FAQ](https://www.gnu.org/licenses/gpl-faq.en.html#LGPLStaticVsDynamic) explains the object-file/relinking requirement for static LGPL linking. Consult a qualified reviewer if you need a formal legal assurance.
