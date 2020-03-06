---
layout: default
title: DBIC PC setup
parent: equipment
nav_order: 2
has_children: true
permalink: /equipment/dbic_pcsetup
---


# Dartmouth fMRI PC setup
![tasks]({{ site.url }}/images/dbic_setup.png)

### fMRI jack: XAF-09 in Moore B75 on "fmri-private network (VLAN 2554)""

### medoc computer
* medoc.dartmouth.edu
* ip: 10.64.1.10
* netmask: 255.255.255.240
* default gateway: 10.64.1.1

### spacetop computer
spacetop.dartmouth.edu
* ip: 10.64.1.9
* netmask: 255.255.255.240
* default gateway: 10.64.1.1

### Note from research computing:
If you need to communicate with other systems outside of the fMRI private network besides 129.170.17.4 and 10.232.11.5 then the ACLs on the network will have to be modified.

### If help needed,
contact Andrew Knutsen, Technology Support Specialist
or Heejung Jung, who helped set up.
