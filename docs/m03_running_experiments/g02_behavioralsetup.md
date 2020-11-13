---
layout: default
title: Behavioral setup
parent: Running experiments
permalink: /runningexp/bsetup
nav_order: 2
---

# Behavioral Testing room Equipment setup
{: .no_toc }
{: .fs-11 }


<!-- ## Table of contents
{: .no_toc .text-delta } -->

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }

1. TOC
{:toc}
</details>

# DBIC daily setup



step 1
{: .label .label-blue}
## Scanner Projector Computer
{: .d-inline-block .fs-6}

* [ ] Log in: [ username: mruser, password: mruser ]
* [ ] On login, Chrome automatically brings up login + pass for projector control
* [ ] turn projector on (this takes 7 minutes) in the scanner project PC.
* [ ] When running experiment, always make sure `Shutter off`
* [ ] + Check projector settings by clicking on the `status` menu
{: .fs-3 .px-6}


---

# Dartmouth fMRI PC setup
{: .d-inline-block}
Maintained by Heejung
{: .label .label-green }
![tasks]({{ site.url }}/images/dbic_setup.png)

fMRI jack:
{: .fs-6}
XAF-09 in Moore B75 on "fmri-private network (VLAN 2554)""
{: .fs-3}

medoc computer
{: .fs-6}
* medoc.dartmouth.edu
* ip: 10.64.1.10
* netmask: 255.255.255.240
* default gateway: 10.64.1.1
{: .fs-3}

spacetop computer
{: .fs-6}
* spacetop.dartmouth.edu
* ip: 10.64.1.9
* netmask: 255.255.255.240
* default gateway: 10.64.1.1
{: .fs-3}

Note from research computing:
{: .fs-6}
If you need to communicate with other systems outside of the fMRI private network besides 129.170.17.4 and 10.232.11.5 then the ACLs on the network will have to be modified.
{: .fs-3}

If help needed,
{: .fs-6}
contact Andrew Knutsen, Technology Support Specialist
or Heejung Jung, who helped set up.
{: .fs-3}

## manually changing IP on linux
* follow this page to change the ip. [link](https://www.linuxtechi.com/assign-static-ip-address-ubuntu-20-04-lts/#:~:text=Configuring%20a%20static%20ip%20address,and%20then%20choose%20wired%20settings.&text=In%20the%20next%20window%2C%20Choose,gateway%20and%20DNS%20Server%20IP.)
* make sure to change the name of this ethernet setting:
Wired > identity > name : spacetop.dartmouth.edu

## Setting firewalls and allowing private network
* ping the medoc PC from the spacetop stim PC
* if it doesn't work, there are two things that need to happen
>> Create a new rule:
[creating rules](https://www.howtogeek.com/112564/how-to-create-advanced-firewall-rules-in-the-windows-firewall/)
>> Frewall > Inbound rules > look for "file and printer sharing (echo Request - ICMPv4-In) Private" > Enable rule
---

# Singularity container
{: .d-inline-block }
move elsewhere
{: .label .label-green}
---

# Installing PTB on linux
{: .d-inline-block }
move elsewhere
{: .label .label-green}
check installation
* neurodebian
* neurodocker
* anaconda
* singularity


worked for Luke
 http://neuro.debian.net/install_pkg.html?p=psychtoolbox-3-common

 Yarik suggestion
 You need to add contrib (probably no need for non-free) portion in addition to main in your NeuroDebian apt file.
* https://wiki.debian.org/SourcesList
* `cat /etc/apt/sources.list.d/neurodebian.sources.list`


Getting error message:
> libGL error: MESA_LOADER: failed to open readeonsi (search paths /usr/lib/x86_64-linux-gnu/dri:\$${ORIGIN}/dri:/usr/lib/dri)
libGL error: failed to load driver: readeonsi
failed to create dri screen

-> https://psychtoolbox.discourse.group/t/matlab-crashes-after-insatlling-ptb-com-jogamp-opengl-glexception/74

# adding EOL to matlab path without having to add it everytime
* check `sudo vim /etc/ptb3/matlab.sh`
* added a matlab path:
EOL MASTER = /home/spacetop/repos/EOL-master
in the shell script
add the line ```export MATLABPATH=$(find "$EOL_MASTER" -type d | grep -v private | tr '\n' ':')$MATLABPATH```

## firewall
* allow incoming input from medoc PC
* use iptable
* ```iptables -A OUTPUT -p tcp -d 192.168.0.114 --dport 20121 -j ACCEPT```
* https://serverfault.com/questions/183461/how-do-i-allow-outgoing-connections-via-iptables
