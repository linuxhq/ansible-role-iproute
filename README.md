# ansible-role-iproute

[![Build Status](https://travis-ci.org/linuxhq/ansible-role-iproute.svg?branch=master)](https://travis-ci.org/linuxhq/ansible-role-iproute)
[![Ansible Galaxy](https://img.shields.io/badge/ansible--galaxy-iproute-blue.svg?style=flat)](https://galaxy.ansible.com/linuxhq/iproute)
[![License](https://img.shields.io/badge/license-GPLv3-brightgreen.svg?style=flat)](COPYING)

RHEL/CentOS - Advanced IP routing and network device configuration tools

## Requirements

None

## Role Variables

Available variables are listed below, along with default values:

    iproute_ematch_map:
      1: cmp
      2: nbyte
      3: u32
      4: meta
      7: canid
      8: ipset
    iproute_group:
      0: default
    iproute_nl_protos:
      0: rtnl
      1: unused
      2: usersock
      3: fw
      4: tcpdiag
      5: nflog
      6: xfrm
      7: selinux
      8: iscsi
      9: audit
      10: fiblookup
      11: connector
      12: nft
      13: ip6fw
      14: dec-rt
      15: uevent
      16: genl
      18: scsi-trans
      19: ecryptfs
      20: rdma
      21: crypto
    iproute_rt_dsfield:
      0x00: default
      0x02: mincost
      0x04: reliability
      0x08: throughput
      0x10: lowdelay
      0x20: priority
      0x28: AF11
      0x30: AF12
      0x38: AF13
      0x40: immediate
      0x48: AF21
      0x50: AF22
      0x58: AF23
      0x60: flash
      0x68: AF31
      0x70: AF32
      0x78: AF33
      0x80: flash-override
      0x88: AF41
      0x90: AF42
      0x98: AF43
      0xa0: critical
      0xc0: internet
      0xe0: network
    iproute_rt_protos:
      0: unspec
      1: redirect
      2: kernel
      3: boot
      4: static
      8: gated
      9: ra
      10: mrt
      11: zebra
      12: bird
      13: dnrouted
      14: xorp
      15: ntk
      16: dhcp
      246: gated/default
      247: gated/inet
      248: gated/conn
      249: gated/static
      250: gated/rip
      251: gated/ospfase
      252: gated/ospf
      253: gated/bgp
      254: gated/aggr
    iproute_rt_realms:
      0: cosmos
    iproute_rt_scopes:
      0: global
      200: site
      253: link
      254: host
      255: nowhere
    iproute_rt_tables:
      0: unspec
      253: default
      254: main
      255: local

## Dependencies

None

## Example Playbook

    - hosts: servers
      roles:
        - role: linuxhq.iproute
          iproute_rt_tables:
            0: unspec
            99: openvpn
            253: default
            254: main
            255: local

## License

Copyright (C) 2018 Taylor Kimball <tkimball@linuxhq.org>

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program. If not, see <http://www.gnu.org/licenses/>.
