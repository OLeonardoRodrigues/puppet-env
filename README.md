# Puppet Env

A simple Puppet Environment using Vagrant.

## Overview

Vagrant is a tool to provision VMs easily and with repeatability.

Puppet is a tool to manage configurations across your infrastructure.

This setup aims to create the basic setup for running a Puppet Environment.

## How To Run

- [Clone this repository](https://github.com/OliveiraLeonardo17/puppet-env.git);
- [Install Vagrant](https://www.vagrantup.com/docs/installation);
- [Install VirtualBox](https://www.virtualbox.org/wiki/Downloads);
- Navigate to the root of this repository on your local machine;
- Execute the command: `vagrant up`;
- Wait for the execution;
- Access [any of the VMs](#available-vms) using `vagrant ssh <VM-Name>`;
- Practice your Puppet skills;

## Available VMs

- 1 Puppet Server/Master;
- How Many Puppet Nodes/Agents you want;
- 1 Puppet DB - Optional; [TODO]
