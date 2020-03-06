---
layout: default
title: equipment
nav_order: 2
has_children: true
permalink: /equipment
---
# equipment

# Project Timeline
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

## 1. dartmouth TSA

social influence task related issues
This is a lengthy report that doesn’t fit well in a slack channel, but I wanted to update and receive input from relevant people. After testing since last weekend, I’ve made some major changes to the pain task in social, and it works relatively well (although I’m not getting my hopes up yet).

#### A. issue:
there was a built-in second when triggering the thermodes.
some trials would not trigger.
timing of the thermode program was longer than 6.5 sec, even accounting for the built-in one sec.

#### B. observation:
It takes 2 seconds to trigger the program
The trials would not trigger when the jitter was shorter than 1 sec
The program lasts for 7 ~ 7.5 sec (even when its coded for 6.5 sec)

#### C. fixes:
Utilizing the main function, there are 3 components to the thermode program : start / trigger / stop. instead of auto trigger, I’ve used manual trigger, meaning that the code will have a “start” and a “trigger”, instead of relying on one “start” component
Changed short jitters to longer ones (0~4 sec → 1~4 sec)

#### D. benefits:
Resolves issue 1): With manual control, we gain control over thermode triggering. No longer do we have a built-in second when triggering.
Somewhat resolves Issue 2): Updated code worked for three tests. Only saw an error if the matlab script was operated multiple times in a row. Closing the medoc program after every run resolves this issue (at least for three tests that I did most recently, however, cannot guarantee. Will continue to test + will ask Boulder to continue to count triggered trials).

#### E. request for boulder: @Mickela Heilicher @Mia Koski @pkragel
Changing the medoc test programs (will attach screen shots of the programs in thread )
changing the matlab scripts (pushed to git)
integrating biopac function into the matlab script (someone at boulder will have to integrate it OR send me the code that is utilized at Boulder)

#### F. Remaining issues: @tor
Issue 3) timing of the thremode is still longer than 6.5 sec. The program takes 2~3.5 sec to reach the designated temperature, which is different from the planned-out 1.7 sec. The medoc always adds 1~1.5 sec to the program, and this is out of my hands.

Should I change the rampup speed, or lengthen the time of the experiment?
Regarding Ramp-up speed: The TSA-II here at Dartmouth allows for a ramp-up/down of 13 sec, whereas the one in Boulder was a max of 10 sec.
If we change the timing of the pain task, we’d probably have to change this for the cognitive/vicarious tasks
I got rid of the jitter before the thermode triggering, which changes the structure of the pain task compared to the cognitive/vicarious task. Should I add back a jitterto the pain task?
