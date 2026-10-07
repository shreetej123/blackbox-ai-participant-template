# round-2 — Investigate

**Team:** BB-XXX
**Queries used:** 12 / budget

## What we concluded

The result score depends on combinations of query-console parameters. The strongest observed positive dependency is between clearance_level and linked_badges, while the strongest observed negative dependency is between badge_age_days and recent_denials. escorts, history_score, and requested_zone also show a combined negative effect. anomaly_ratio and tenure_years show only a weak positive effect, while site has a weak/nearly neutral effect.
<!-- The short version. What is this system doing? -->

## How we got there

We changed parameters in pairs or groups and recorded the resulting score. Increasing badge_age_days and recent_denials changed the score from 0.8213 to 0.7325, while reversing both increased it to 0.8243. Increasing clearance_level and linked_badges changed the score from 0.8243 to 0.8746. Reversing them reduced it to 0.8053. Changes to anomaly_ratio and tenure_years produced only small score movements. Changes to escorts, history_score, and requested_zone together produced a substantial decrease, while reversing them increased the score.

<!-- The experiments that mattered, in order. Why each one was worth a query. -->

## What we ruled out

We ruled out site as a major driver based on the A → B → C → D → A tests, which produced only small changes in the result. We also ruled out anomaly_ratio and tenure_years as strong drivers based on their relatively small observed score changes.
<!-- Hypotheses you rejected and what killed them. This section carries real marks. -->

## What we are still unsure about

The individual contribution of each parameter within a pair or group has not been isolated. The current evidence establishes combined dependencies, but additional queries changing one parameter at a time are needed to determine the exact individual effect and whether there are interaction effects between parameters.
<!-- Being honest here scores better than overclaiming. -->
