# Grading rubric — Assignment 3: Anomaly Detection

**10 points, graded for completion.** As with the earlier assignments, if the
notebook runs end to end and each part does what it asks, you get full credit.
Detection quality is *not* graded; a model with a mediocre AUC and a working
pipeline is 10/10.

| # | Item | Pts |
|---|---|---|
| **Part 1 — Warmup** | | **1** |
| 1.1 | Run the provided OCSVM demo end to end on the demo trace: flows built, model trained, a metric printed | 1 |
| **Part 2 — Other anomaly-detection models** | | **3** |
| 2.1 | Run a second `netml` model (autoencoder, GMM, isolation forest, KDE, or PCA) on the same demo data | 1 |
| 2.2 | Run a third `netml` model on the same demo data | 1 |
| 2.3 | **Write a sentence or two** on which model(s) tend to perform better, citing the numbers you compared | 1 |
| **Part 3 — Activity detection on the provided device traces** | | **6** |
| 3.1a | Build `netml` flows from at least one of the provided smart-home device traces | 1 |
| 3.1b | Parse that device's label file and align its activity timestamps with the trace's time base, **with a sentence** on how the alignment was done | 1 |
| 3.2a | Assign each flow a label (idle vs. active, or categorical by activity) from the activity windows: `netml`'s `label_flows`, an override of it, or your own labeling function | 1 |
| 3.2b | **Briefly explain** the labeling scheme: which windows count as active, and how flows that span a window boundary are handled | 1 |
| 3.3a | Train one unsupervised `netml` model on idle flows and apply it to idle plus active flows | 1 |
| 3.3b | Report at least one evaluation metric (AUC, F1, confusion matrix, etc.) **with a sentence** on what it says about detecting device activity | 1 |

## Requirements that gate the score

- **The notebook must run.** Submit it *executed* (outputs saved). A notebook
  with error tracebacks in the cells that implement graded items, or with no
  outputs at all, is treated as not running: those items earn 0 until fixed
  and resubmitted.
- **Sub-items are all-or-nothing.** Each row is 1 point if done in good faith,
  0 if absent. There are no half points; "did the thing" is the bar.
- **Written answers count.** Items 2.3, 3.1b, 3.2b, and 3.3b require a
  sentence or two of explanation, not just code.
- **One device is enough.** Part 3 asks you to work with one or more of the
  device traces. One trace and one activity type (e.g., music playing vs.
  idle on the Google Home) earns full credit; more devices or activity types
  are a nice touch, not required.
- **Data.** The demo trace, the device traces, and their label files are in
  [noise-courses/data](https://github.com/noise-courses/data) under
  `anomaly-detection/`; the notebook expects that repository cloned at `data/`.
  If you put the files elsewhere, fix the paths; paths are not graded. Do not
  commit the pcaps (the largest is about 74 MB); committing them is harmless
  but slow.
- **AI use.** Encouraged, but acknowledge it in the notebook and be ready to
  explain your code. Not acknowledging AI use does not cost points on this
  assignment, but see the syllabus on assessment of understanding.

## Late policy

Due 11:59 p.m. Chicago time on the due date; 96-hour grace balance for the term,
then half credit within one week, then zero. See the syllabus.
