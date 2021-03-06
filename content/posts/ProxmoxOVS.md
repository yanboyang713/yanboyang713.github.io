---
title: "Getting Started Set-up OVS for Proxmox"
date: 2021-12-06T12:58:00+08:00
tags: ["OVS"]
categories: ["Cluster"]
draft: false
---

## Introduction {#introduction}


## Install Open vSwitch {#install-open-vswitch}

Update the package index and then install the Open vSwitch packages by executing:

```console
 apt update
 apt install ifupdown2
 apt install openvswitch-switch
```

root@pve-home:~# cat _etc/network/interfaces
<https://karneliuk.com/2021/08/infrastructure-1-building-virtualized-environment-with-debian-linux-and-proxmox-on-hp-and-supermicro>_

ifreload -a
ifup vmbr0

```file
auto lo
iface lo inet loopback

auto enp6s0
iface enp6s0 inet manual

auto enp1s0
iface enp1s0 inet manual

auto enp2s0
iface enp2s0 inet manual

auto enp3s0
iface enp3s0 inet manual

auto enp5s0
iface enp5s0 inet manual

auto ens9
iface ens9 inet manual

auto vlan1
iface vlan1 inet static
        address 192.168.1.2/24
        gateway 192.168.1.1
        ovs_type OVSIntPort
        ovs_bridge vmbr0
        ovs_options vlan_mode=access
        ovs_extra set interface ${IFACE} external-ids:iface-id=$(hostname -s)-${IFACE}-vif
        dns-nameservers 192.168.1.1 8.8.8.8 8.8.4.4

auto bond0
iface bond0 inet manual
        ovs_bonds enp1s0 enp2s0 enp3s0 ens9 enp5s0
        ovs_type OVSBond
        ovs_bridge vmbr0
        ovs_options vlan_mode=native-untagged bond_mode=balance-slb

auto vmbr0
iface vmbr0 inet manual
        ovs_type OVSBridge
        ovs_ports bond0 vlan1
```
