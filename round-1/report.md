# round-1 — Observe

**Team:** BB-008
**Queries used:** 74 / budget

## What we concluded

We found that decreasing `linked_badges` improved the score in our tested configuration.

The strongest results were:

- `linked_badges = 20` → 0.9899
- `linked_badges = 19` → 0.9942
- `linked_badges = 18` → **0.9945**

Our current best score is **0.9945** with `linked_badges = 18`.
<!-- The short version. What is this system doing? -->

## How we got there

We tested different values of `linked_badges` and compared the resulting scores.

- Query 56: `linked_badges = 20` → 0.9898
- Query 71: `linked_badges = 20` → 0.9899
- Query 73: `linked_badges = 19` → 0.9942
- Query 74: `linked_badges = 18` → 0.9945

The score improved as `linked_badges` decreased from 20 to 19 and then to 18.

<!-- The experiments that mattered, in order. Why each one was worth a query. -->

## What we ruled out

We ruled out `linked_badges = 20` as our best tested value because lower values produced higher scores.

The score of 0.9899 at `linked_badges = 20` was beaten by 0.9942 at 19 and 0.9945 at 18.
<!-- Hypotheses you rejected and what killed them. This section carries real marks. -->

## What we are still unsure about

We also need more testing to determine whether the observed improvement remains consistent across different configurations. Therefore, we cannot yet conclude that `linked_badges = 18` is the global optimum.

<!-- Being honest here scores better than overclaiming. -->
