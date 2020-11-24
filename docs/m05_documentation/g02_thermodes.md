---
layout: default
title: Thermodes documentation
parent: Documentation
permalink: /doc/thermodes
nav_order: 1
---

# Protocols
{: .no_toc }
{: .fs-11 }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{: .no_toc}

# Thermode rules

## Medoc code
https://github.com/canlab/CanlabPrivate/tree/master/pathwaySupportCode
* step 1: add this pathwaysupportcode folder to matlab path
* step 2: use two lines of code in your experiment script:
```
main(ip, port, 1, program_number) # 1 SELECTS program and launches in the background
# allow for some time in between at least 4 seconds: e.g. select the program during a jitter and trigger the program after the jitter
main(ip, port, 4, program_number) # 4 TRIGGERS program
```
* step 3: in conjunction, make sure that the stimulation program options are set as follows:
In the specific stimulation program, go to option trigger > select manual for trial in dropdown menu

## Manual trigger
### Reasons for manual trigger
* there is always a *1 sec* delay when the medoc program is initiated. In order to avoid this 1 second lag,
we will select the program in the background, and trigger it at the intended time.
This is essentially what main(ip, port, 1, program_number), and main(ip, port, 4, program_number) is doing

### When does a lag occur? - auto Trigger
Let's say that I used the following configuration

specific stimulation program > option trigger > select auto
External control: automatic start
Program > time before sequence : 0
The program will start immediately. However, there will be a time lag from starting the program. Specifically, the time to run the line main(ip,port, 1, program) and the time to see the blue background with the program amounts to one second.

This became an issue when we needed our imaging studies to run precisely within a timeframe, because it was always adding 1 sec * number of trials to the experiment.

## Plugging in programs

## naming convention
for standardization, let's stick with
`PROJECT_temp-XX_dur-XX_8bit-XX`
* the 8 bit code is necessary - mind you, 8 bit codes cannot overlap.
For example, if you've plugged in numbers from 45-50, the next experimenter cannot use those numbers.
In order to help the next experimenter, please indicate which 8bit codes you've used.
We're not good with reading binary numbers - please indicate the decimal version


## participant login
* ![thermode_default]({{ site.url }}/images/BIDS_default.png)
* ![thermode_BIDS]({{ site.url }}/images/BIDS_format.png)
{: .d-inline-block .fs-6}

* lastname: `ses-XX`
* first name: `sub-XXXX`
* ID: `spacetop_ses-XX_sub-XXXX` (each ID should be unique, otherwise it will throw an error)
* Gender : `M/F`
* Date of Birth : `date of experiment` (click on dropdown menu, calendar default is the date of experiment)
* Doctor: Your initials

## checking thermode OUTPUT
* at the end of each session, we will count the number of trials that were triggered.
* We will also export the results to a flashdrive.
---

# Social Influence parameters
* ![social_47]({{ site.url }}/images/spacetop_social_47.jpg)
* ![social_48]({{ site.url }}/images/spacetop_social_48.jpg)
* ![social_49]({{ site.url }}/images/spacetop_social_49.jpg)

---

# Learning task parameters
* ![learning_45]({{ site.url }}/images/spacetop_learning_45.jpg)
* ![learning_46]({{ site.url }}/images/spacetop_learning_46.jpg)
* ![learning_47]({{ site.url }}/images/spacetop_learning_47.jpg)
* ![learning_48]({{ site.url }}/images/spacetop_learning_48.jpg)
* ![learning_49]({{ site.url }}/images/spacetop_learning_49.jpg)
* ![learning_50]({{ site.url }}/images/spacetop_learning_50.jpg)
