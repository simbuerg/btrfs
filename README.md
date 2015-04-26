# btrfs-pp - Pretty Printers for btrfs-progs tools

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
