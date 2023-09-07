# Overview

Simple barebones VMs that can be created ad-hoc and provisioned with Ansible

# Vagrant

Currently includes the following VMs which use VMware (Apple Silicon, x86_64) or VirtualBox (x86_64) as the provider. All VMs will by default be installed with a Datadog Agent with every feature enabled and a Vector agent.

- Ubuntu 22.04
- Ubuntu 20.04

Configure the [Vagrantfile](Vagrantfile) to choose which VMs to create.

Requires Ansible to be installed for VM provisioning.

```bash
# On first run or when recreating VMs your DD_API_KEY is required
DD_API_KEY="<your key>" vagrant up
vagrant destroy && DD_API_KEY="<your key>" vagrant up

# On subsequent runs when suspending and resuming your DD_API_KEY is not required
vagrant suspend
vagrant up
```

# Base Images

The default base images used in these configurations are built by Packer in [golden-images](https://github.com/johnrichter/golden-images) and uploaded to Vagrant Cloud.

# TODO

- [ ] Move Ansible roles to an independent repo
