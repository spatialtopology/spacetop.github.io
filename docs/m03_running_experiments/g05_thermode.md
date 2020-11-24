---
layout: default
title: Register Thermode
parent: Running experiments
permalink: /runningexp/tsa2
nav_order: 4
---

# Register participant in Medoc (Thermode)
{: .no_toc }
{: .fs-11 }


* ![thermode_default]({{ site.url }}/images/BIDS_default.png)
* ![thermode_BIDS]({{ site.url }}/images/BIDS_format.png)
{: .d-inline-block .fs-6}



* lastname: `ses-XX`
* first name: `sub-XXXX`
* ID: `spacetop_ses-XX_sub-XXXX` (each ID should be unique, otherwise it will throw an error)
* Gender : `M/F`
* Date of Birth : `date of experiment` (click on dropdown menu, calendar default is the date of experiment)
* Doctor: Your initials

----

# Also documented in DBIC setup

## Medoc PC: Medoc TSA setup
{: .d-inline-block }
{: .fs-6}

* [ ] Turn TSA-II on before experiment, for safety test to pass
* [ ] check green light on TSA-II
* [ ] check connection between TSA-II & medoc-PC (USB!!)
* [ ] Turn Medoc PC on and open Acknowledge software (admin/admin)
* [ ] Click participant, test, and make sure "external control" is on.
{: .fs-3 .px-6}
    * External control “on”: External control > check box
{: .fs-3 .px-7}
* [ ] plug in participant information (use BIDS id)
{: .fs-3 .px-6}


## Medoc PC - Stim PC communictaion
* [ ] Check if all of the ethernet cables are connected [ #LINK configuration ]
* [ ] Test 1: In the SPACETOP PC terminal, type  ping 10.64.1.10 This is the ip address of the medoc PC. we’ll make sure that the spacetop can send bytes to medoc
* [ ] Test 2: turn on medoc main station program. Go into external control mode.
In the SPACETOP PC, load matlab ptb3-matlab. In the command window,
main(‘10.64.1.10’, 20121, 1, 100) # select Program
main(10.64.1.10’, 20121, 4, 100) # Trigger Program
* [ ] run `testmain.m`, which will basically do Test 2 for you.
