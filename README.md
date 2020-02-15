# vagrant-open-mpi
Open MPI bootstrap example with vagrant

## Summary
A simple setup for creating a N size cluster of ubuntu nodes with openmpi configured. The amount of nodees can be configured by uppdating the value `N_VMS` in the `Vagrantfile`

## Installation

1. install virtualbox
1. install vagrant
1. clone this repository
1. cd in to the root of this repository
1. run `vagrant up`

## Usage

To SSH into any of the nodes simply run: `vagrant ssh node<N>` (i.e. `node1`)
You'll find any files in the `./data` directory synced to the mounted `/data` directory on each of the nodes.


To compile and execute `make build-and-run TARGET=/data/hello-world/hello-world NODES=node1,node2,node3` in the terminal

