![alt text](https://raw.githubusercontent.com/Fermat-ORG/media-kit/00135845a9d1fbe3696c98454834efbd7b4329fb/MediaKit/Logotype/fermat_logo_3D/Fermat_logo_v2_readme_1024x466.png "Fermat Logo")

# IoP CAN NET iptb

> This is our implementation of iptb.

In order to keep this neat and tidy, we have written our documentation at:
[IoP CAN NET DOCs](https://github.com/Fermat-ORG/iop-content-address-network-documentation).

Original content follows:



# IPTB
`iptb` is a program used to create and manage a cluster of sandboxed IPFS nodes locally on your computer. Spin up 1000s of nodes! It exposes various options, such as different bootstrapping patterns. `iptb` makes testing IPFS networks easy!

### Example

```
$ iptb init -n 5

$ iptb start
Started daemon 0, pid = 12396
Started daemon 1, pid = 12406
Started daemon 2, pid = 12415
Started daemon 3, pid = 12424
Started daemon 4, pid = 12434

$ iptb shell 0
$ echo $IPFS_PATH
/home/noffle/testbed/0

$ echo 'hey!' | ipfs add -q
QmNqugRcYjwh9pEQUK7MLuxvLjxDNZL1DH8PJJgWtQXxuF

$ iptb shell 4
$ ipfs cat QmNqugRcYjwh9pEQUK7MLuxvLjxDNZL1DH8PJJgWtQXxuF
hey!
```

### Usage
```
$ iptb --help

NAME:
	iptb - The IPFS TestBed

USAGE:
	iptb [global options] command [command options] [arguments...]

COMMANDS:
	init			create and initialize testbed configuration
	start			start up all testbed nodes
	kill, stop		kill a specific node (or all nodes, if none specified)
	restart			kill all nodes, then restart
	shell			spawn a subshell with certain IPFS environment variables set
	get			get an attribute of the given node
	connect			connect two nodes together
	dump-stack		get a stack dump from the given daemon
	help, h			show a list of subcommands, or help for a specific subcommand

GLOBAL OPTIONS:
	--help, -h		show help
	--version, -v		print the version
```

### Install

```
go get github.com/whyrusleeping/iptb
```

### Configuration

By default, `iptb` uses `$HOME/testbed` to store created nodes. This path is
configurable via the environment variables `IPTB_ROOT`.



### License

MIT
