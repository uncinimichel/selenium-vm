selenium-vm
===========

## Pre-requisite

Run: 
`vagrant plugin install vagrant-omnibus`

This repo containing `Vagrantfile` which has `selenium-grid` vm in it.

## Requirements
These tools needs to be installed in your machine. 
- [Virtualbox](https://www.virtualbox.org)
- [Vagrant](http://www.vagrantup.com/)

## How to use

- Clone this repository and do `vagrant up <vm-name>` from inside the repo cloned.
- Run selenium test with selenium hub url as `http://macpro-b8944d:4444/wd/hub`

## Hub + node
Set up selenium hub url `export SELENIUM_HUB_URL=192.X.X.X`
To bring up hub + node vm `vagrant up selenium-grid`

## Add more nodes
`vagrant up node1` up to `node3`
Add more vms to your Vagrantfile if this not sufficient.
