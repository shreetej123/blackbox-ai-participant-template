# round-2 — Investigate

**Team:** BB-XXX
**Queries used:** 20 / budget

## What we concluded

The observed results show a negative dependency between badge_age_days and recent_denials and a positive dependency between clearance_level and linked_badges. The experiments also indicate combined effects involving escorts, history_score, and requested_zone. Changes to anomaly_ratio and tenure_years produced comparatively smaller score changes, while the tested site changes showed little effect.

## How we got there

We changed parameters in pairs or groups and recorded the resulting score. Increasing badge_age_days from 46.5 to 47.5 and recent_denials from 2.5 to 3.5 changed the score from 0.8213 to 0.7325. Reversing those changes increased the score to 0.8243. Increasing clearance_level from 50 to 52 and linked_badges from 10 to 12 changed the score from 0.8243 to 0.8746, while reversing those changes reduced it to 0.8053. Additional paired and grouped changes were used to examine the remaining parameters.


<!-- The experiments that mattered, in order. Why each one was worth a query. -->

## What we ruled out

We found no substantial observed effect from the tested site changes. The changes involving anomaly_ratio and tenure_years also produced relatively small score movements compared with the larger paired changes observed above.


## What we are still unsure about


The individual contribution of each parameter within a pair or group has not been isolated. The current evidence establishes combined dependencies, but additional controlled queries changing one parameter at a time are needed to determine the individual effects and possible interaction effects.
