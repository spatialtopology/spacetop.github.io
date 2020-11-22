---
layout: default
title: Register Biopac
parent: Running experiments
permalink: /runningexp/biopac
nav_order: 5
---

# Register participant in Acqknowledge (Biopac)
{: .no_toc }
{: .fs-11 }


Biopac template tree structure on DBIC medoc PC
{: .fs-6 }
```
+---biopac_template
|   +---ses-01
|   |       ALIGNVIDEOS_spacetop_sub-XXXX_ses-01_task-alignvideos.gtl
|   |       SOCIAL_spacetop_sub-XXXX_ses-01_task-social.gtl
|   |
|   +---ses-02
|   |       ALIGNVIDEOS_spacetop_sub-XXXX_ses-02_task-alignvideos.gtl
|   |       FACES_spacetop_sub-XXXX_ses-02_task-faces.gtl
|   |       NARRATIVES_spacetop_sub-XXXX_ses-02_task-narratives.gtl
|   |
|   +---ses-03
|   |       ALIGNVIDEOS_spacetop_sub-XXXX_ses-03_task-alignvideos.gtl
|   |       LEARNING_spacetop_sub-XXXX_ses-03_task-learning.gtl
|   |
|   \---ses-04
|           ALIGNVIDEOS_spacetop_sub-XXXX_ses-04_task-alignvideos.gtl
|           FRACTIONAL_MEMORY_spacetop_sub-XXXX_ses-04_task-fractional-memory.gtl
|           FRACTIONAL_POSNER_spacetop_sub-XXXX_ses-04_task-fractional-posner.gtl
|           FRACTIONAL_SAXE_spacetop_sub-XXXX_ses-04_task-fractional-saxe.gtl
|           FRACTIONAL_SPUNT_spacetop_sub-XXXX_ses-04_task-fractional-tomspunt.gtl
|           SOCIAL_spacetop_sub-XXXX_ses-04_task-social.gtl
|
\---data
    \---sub-0003
            ALIGNVIDEOS_spacetop_sub-0003_ses-01_task-alignvideos.acq
            LEARNING_spacetop_sub-0003_ses-03_task-learning.acq

```
{: .fs-3}

* for each session, open the following .gtl templates
* in order to prevent losing any data, save the `.gtl` template with the corresponding participant name. Make sure to save as `.acq`
* use ctrl + space to start and stop (the button is misleading to use)
* stop between runs
    * e.g. social influence has 3 runs. Use `ctrl + space` to stop at the end of run 1, `ctrl + space` to start for run 2
* at the end of the entire experiment, save the template as .acq.
{: .fs-6 }
