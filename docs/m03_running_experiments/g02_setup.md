---
layout: default
title: Equipment setup
parent: Running experiments
permalink: /runningexp/ST
nav_order: 2
---

# Equipment setup
{: .no_toc }
{: .fs-11 }


## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

# DBIC PC setup + DBIC daily setup

## 1. Projector Computer
* Log in: [ username: mriuser, password: mriuser ]
* On login, Chrome automatically brings up login + pass for projector control
* turn projector on (this takes 7 minutes)
* When running experiment, always make sure "Shutter off"
* + Check projector settings by clicking on the “status” menu

---

## 2. Stim PC and MRI devices
* Screen: Plug video VGA via USB-C adapter to Stim PC

#### For Audio:
* Turn on Volume box: Pyle. Stereo power amplifier 2x15w
* Plug audio splitter (aux cable) to Stim PC

#### For Response:
* Configure button box
      * For 2-button box: select HID key 2x2 12345
      * For trackball: select track
* Plug button box USB to Stim PC
* If using multiple response devices, be ready for switching out devices
* Prep Trackball in advance and put “on deck”

---

## 3. Screening form
* Get safety screening signed
* Log participant into REDcap system
* (Chrome comes on automatically which allows adding a participant)
    1. Dartmouth id > SID
    2. Gender (default female. Double check if participant is male!)
    3. Race/ethnicity (information should be filled in safety form)
    4. Make sure to get the correct DBIC study number in
* Add SID and accession number to scanner notebook
* Add SID and accession number to ST_participant spreadsheet

---

## 4. Medoc
* Turn TSA-II on before experiment, for safety test to pass
* Turn Medoc PC on and open Medoc software
* Click participant, test, and make sure "external control" is on.
    * External control “on”: External control > check box
* Connect to experiment computer

---

## 5. Matlab
* Open all relevant tasks during T1
* Double-check participant - we cannot mess this one up
* Pay attention when runs start and end
* Start key will be ‘s’ before the trigger.
* End key will be ‘e’

---

## 6. After scanning
* [ ] Pull out trigger / audio from pc
* [ ] Restock the scrubs
* [ ] If laundry basket full, take it up
* [ ] Turn the TV / lights off

---


# TSA-II
* plug TSA-II cord and medoc-PC cord
* wait until TSA-II turns green
* connect TSA-II USB to medoc-PC
* open medoc softward on medoc-PC
* check if `external control` is "enabled"
* plug in participant information (use BIDS id)

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
* spacetop.dartmouth.edu
* ip: 10.64.1.9
* netmask: 255.255.255.240
* default gateway: 10.64.1.1

### Note from research computing:
If you need to communicate with other systems outside of the fMRI private network besides 129.170.17.4 and 10.232.11.5 then the ACLs on the network will have to be modified.

### If help needed,
contact Andrew Knutsen, Technology Support Specialist
or Heejung Jung, who helped set up.


---

# Singularity container - ##NOTE this should be moved elseware

---

# Installing PTB on linux - ##NOTE this should be moved elseware
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
