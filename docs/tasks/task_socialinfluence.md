---
layout: default
title: Social Influence
parent: Task Descriptions
grand_parent: Tasks
nav_order: 5
---
# Social Influence
{: .no_toc }
## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}


## Current GitHub
{: .fs-6 }
under [spatialtopology/socialPain](https://github.com/spatialtopology/social_influence) "private repo"

## Running the experiment
repo > scripts > step01_taskscripts > [RUN_social_influence.m]
(https://github.com/spatialtopology/social_influence/blob/master/scripts/step01_taskscripts/RUN_social_influence.m)
will ask for session number and participant number

## Condition 1. Pain
{: .fs-6 }
<!-- [github TriggerThermode](https://github.com/canlab/Paradigms_Private/blob/master/PAINGEN_paradigms/TriggerThermode.m){: .btn .fs-5 .mb-4 .mb-md-0 } -->


## Condition 2. Vicarious pain
{: .fs-6 }

[original dataset](http://www.pitt.edu/~emotion/um-spread.htm){: .btn .fs-5 .mb-4 .mb-md-0 }
<!-- [CANlab repository](https://github.com/canlab/Paradigms_Public/tree/master/inprep_Lanlan_Perceived_pain_gender_bias){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 } -->

1. original dataset
{: .fs-4 }
* UNBC-McMaster Shoulder Pain Expression Archive Database
* Reference: Lucy, P., Cohn, J. F., Prkachin, K. M., Solomon, P., & Matthrews, I. (2011). Painful data: The UNBC-McMaster Shoulder Pain Expression Archive Database. IEEE International Conference on Automatic Face and Gesture Recognition (FG2011)

2. filtered dataset
* have selected 3 videos per participant (low, med, high pain)
* each video: duration of 4 seconds
* how are videos generated:

1) download videos from UNBC database and place in resources. (Will not be uploaded in git due to storage issues)

2) social_influence > scripts > step00_experimentDev > create_videos > create_videos_96frames.py
each video has a PSPI rating. the idea is to create a 4 sec video around the max PSPI rating

3) select videos via "McMaster_vicarious_videos.ipynb"
output will be in '/Users/h/Dropbox/Projects/socialPain/stimuli/Ratings.csv'

<!-- 2. publication in CANlab
{: .fs-4 }
* CANlab publication:
* CANlab github: https://github.com/canlab/Paradigms_Public/tree/master/inprep_Lanlan_Perceived_pain_gender_bias -->


## Condition 3. cognitive difficulty
{: .fs-6 }
* Mental rotation task
* Reference: Ganis, G., & Kievit, R. A. (2015). A New Set of Three-Dimensional Shapes for Investigating Mental Rotation Processes: Validation Data and Stimulus Set. Journal of Open Psychology Data, 3(1), e3. DOI: http://doi.org/10.5334/jopd.ai
* Repository: https://figshare.com/articles/A_new_set_of_three_dimensional_stimuli_for_investigating_mental_rotation_processes/1045385
