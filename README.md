# btrfs-pp - Pretty Print btrfs-progs

This is a collection of simple 'pretty-printing' functions that combine
the output of different btrfs-progs submodules.

Requires: plumbum
```
pip install plumbum --user
```

## Usage

```
› sudo ./btrfs-pp --help
Various pretty-printers for btrfs diagnostic information
Usage:
    btrfs-pp [SWITCHES] [SUBCOMMAND [SWITCHES]]

Meta-switches:
    -h, --help     Prints this help message and quits
    -v, --version  Prints the program's version and quits

Subcommands:
    quota          Join 'btrfs qgroup show' output with 'btrfs subvolume list' ; see 'btrfs-pp quota --help' for more info
```

## Quota

```
› sudo ./btrfs-pp quota --help
Join 'btrfs qgroup show' output with 'btrfs subvolume list'
Usage:
    btrfs-pp quota [SWITCHES] fspath

Meta-switches:
    -h, --help     Prints this help message and quits
    -v, --version  Prints the program's version and quits

Switches:
    -o             print only subvolumes below specified path
```

This joins the output of btrfs qgroup show <fspath> with
btrfs subvolume list <fspath>.

### Example

```
› sudo ./btrfs-pp quota -o /var/lib/docker/btrfs/subvolumes
Subvolume       Referenced      Exclusive
docker/btrfs/subvolumes/511136ea3c5a64f264b78b5433614aec563103b4d4702f3ba7d4d2698e22c158        16.00KiB        16.00KiB
docker/btrfs/subvolumes/f3c84ac3a0533f691c9fea4cc2ceaaf43baec22bf8d6a479e069f6d814be9b86        194.45MiB       480.00KiB
docker/btrfs/subvolumes/a1a958a248181c9aa6413848cd67646e5afb9797f1a3da5995c7a636f050f537        194.45MiB       112.00KiB
docker/btrfs/subvolumes/9fec74352904baf5ab5237caa39a84b0af5c593dc7cc08839e2ba65193024507        194.45MiB       80.00KiB
docker/btrfs/subvolumes/d0955f21bf24f5bfffd32d2d0bb669d0564701c271bc3dfc64cfc5adfdec2d07        194.45MiB       80.00KiB
```
