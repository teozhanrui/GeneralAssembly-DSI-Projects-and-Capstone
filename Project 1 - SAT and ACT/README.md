# Project 1: SAT & ACT Analysis

#### Author: Teo Zhan Rui

This project comprises 2 notebooks,
1) main.ipynb : All analysis and finding are found here.
2) supplementary.ipynb : Import additional data and prepared data is exported to Tableau for mapping. Please see notebook for source.

## Problem Statement

SAT was redesigned and the new format was rolled out in 2015. Over the years, SAT has gained some grounds in participation rate from some states but did not fare well in other states. This study aims to find out unlying statistical trends to answer the following questions. Thereafter, some recommendations will be proposed based on known good practices to target states with lower SAT participation rates. 

1. How does participation rates affect the total or composite score for SAT and ACT in each state? <br>
2. Does average personal income per capita affect the participation rates in each test? <br>
3. Has performance across the national changed from 2017 to 2018? <br>
4. Which states show significant change in participation between 2017 and 2018 and what was the possible causes? <br>

## Executive Summary

### Keying Findings

1. The total or composite score has strong negative correlation to the participation rates. This suggests some form of selection bias in which states with lower participation results in higher performance. 

2. Majority of wealthier states, with some exceptions, favour SAT over ACT. Most states that mandate compulsory testing using ACT fall in the 'medium' and 'low' income group by states.

3. Using bootstrap sampling and subsequently z-test for hypothesis testing, there is more change in performance in SAT from 2017 to 2018 across the nation.

4. Colorado and Illinois were revealed to have implemented switch from ACT to SAT and state intervention was the key. 

#### my data dictionary

|Feature|Type|Dataset|Description|
|---|---|---|---|
|state|object|sat_2017/ act_2017|State of USA|
|sat_17_par|float|sat_2017|participation rate for SAT 2017|
|sat_17_readwrite|int|sat_2017|state average score for SAT 2017 Reading and Writing|
|sat_17_math|int|sat_2017|state average score for SAT 2017 Mathematics|
|sat_17_total|int|sat_2017|state average of total score for SAT 2017|
|act_17_par|float|sat_2017|participation rate for SAT 2017|
|act_17_eng|float|act_2017|state average score for ACT 2017 English|
|act_17_math|float|act_2017|state average score for ACT 2017 Math|
|act_17_read|float|act_2017|state average score for ACT 2017 Reading|
|act_17_sci|float|act_2017|state average score for ACT 2017 Science|
|act_17_compo|float|act_2017|state average of composite score for ACT 2017|
|sat_change_par|float|final|change in SAT participation rate from 2017 to 2018|
|act_change_par|float|final|change in ACT participation rate from 2017 to 2018|
|avg_income_17|int|income_schools|average personal income per capita by state 2017|
|avg_income_18|int|income_schools|average personal income per capita by state 2018|
|income_group_17|category|income_schools|income groups "low", "medium and "high"|
|income_group_18|category|income_schools|income groups "low", "medium and "high"|
|num_sch|float|income_schools|number of 4 year universities by state|

#### Conclusions
1. The total or composite score has strong negative correlation to the participation rates. This suggests some form of selection bias in which states with lower participation results in higher performance. 

2. Majority of wealthier states, with some exceptions, favour SAT over ACT. Most states that mandate compulsory testing using ACT fall in the 'medium' and 'low' income group by states.

3. Using bootstrap sampling and subsequently z-test for hypothesis testing, there is more change in performance in SAT from 2017 to 2018 across the nation.

4. Colorado and Illinois were revealed to have implemented switch from ACT to SAT and state intervention was the key.

#### Recommendations: 
1. Target Florida as participation rate for both test showed two figure drops. The state does not appear to have preference for either test and there is no compulsory testing in place. Hence might be easier to convince the education board of the merits of SAT. Given that Florida falls in the 'medium' income group, the financial barrier for parents and students to prepare for SAT might be lower. 

2. Common and proven strategies to improve participating in SAT: <br>
    a. mandatory sitting of SAT as requirement for graduation <br>
    b. full fee waiver covered by state for test registration <br>
    c. test preparation to be part of school curriculum <br>
    d. collaboration with private education providers such as Khan Academy to provide online resources for students.
    
    
Source: 

#### Suggestions for Future Studies with Additional Data:
1. income background of candidates
2. type of schools of candidates, state funded or private
3. racial background of candidates

#### Sources: 
1. https://www.brookings.edu/research/race-gaps-in-sat-scores-highlight-inequality-and-hinder-upward-mobility/
2. https://magoosh.com/hs/sat/states-that-require-the-act-or-sat/
3. https://www.coloradokids.org/wp-content/uploads/2016/01/ACTvsSAT_FINAL.pdf
4. https://www.chicagotribune.com/news/ct-illinois-chooses-sat-met-20160211-story.html
5. https://www.latimes.com/california/story/2019-10-31/act-scores
6. https://www.hanoverresearch.com/media/Best-Practices-to-Increase-SAT-Participation-1.pdf

