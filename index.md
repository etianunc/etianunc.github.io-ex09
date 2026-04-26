---
# Do not edit the text between these lines!
layout: default
---

# Project: Should COMP 110 Add an Open-Ended Project?

This page summarizes my analysis exploring the idea: *"The course should have at
least one project that is more open-ended so that people who may not necessarily
be pursuing a comp-centric career can explore ways in which they can connect
their newfound programming skills to other fields."*

## Summary of the Analysis

I combined the two end-of-semester survey CSVs (`survey_izzi.csv` and
`survey_alyssa.csv`) into a single table of 764 student responses. Using the
helper functions from `data_utils.py` (`read_csv_rows`, `columnar`, `head`,
`select`, `count`) plus my own helpers (`rows_where`, `average_of_ints`, and
`top_n_keys`), I looked at three things:

1. **Who is in the course?** I used `count` on the `comp_major` column to break
students down by whether they're pursuing a comp-centric path.
2. **Do non-comp majors want connections to other fields?** I filtered to the
non-comp-major group with my `rows_where` helper and computed the average
`interested_connections` rating (a 1–7 Likert score).
3. **How diverse are the majors?** I used `count` on the `major` column to see
how many distinct fields are represented.

Key numbers from the analysis:

- **713 of 764 students (~93%)** are *not* pursuing a comp-centric major.
- Non-comp majors rate their interest in cross-field connections at **4.39 / 7**
on average, vs. **4.5 / 7** for the class as a whole.
- Students come from **47 different majors**, with biology, neuroscience,
economics, business, data science, psychology, and environmental science being
the most common.

## Visualizations

<!-- Update <custom-path> to match this repository, just like in index.md. -->

### 1. How many students are pursuing a comp-centric path?

<img src="/etianunc.github.io-ex09/static/imgs/chart1_comp_major_counts.png" alt="Countplot of comp_major status showing the 'No' bar far taller than the three 'Yes' bars." width="600"/>

The countplot shows the "No" bar dwarfing the three "Yes" categories — most
students in the class are not on a comp-centric track.

### 2. Average `interested_connections` rating by group

<img src="/etianunc.github.io-ex09/static/imgs/chart2_avg_connections.png" alt="Barplot of average interested_connections rating by comp_major status." width="600"/>

All four groups land between roughly 4 and 5 on the 1–7 scale. Non-comp majors
are not noticeably less interested in cross-field connections than comp majors.

### 3. Distribution of `interesting` ratings by group

<img src="/etianunc.github.io-ex09/static/imgs/chart3_interesting_box.png" alt="Boxplot of how interesting students found the course, split by comp_major status." width="600"/>

This boxplot is the most telling chart. Non-comp majors (the "No" group) have a
lower median and a heavier low-end tail than students pursuing a COMP degree —
which is exactly the engagement gap that an open-ended project could help close.

## Conclusion

The data somewhat supports my idea of adding opportunities to explore
connections to different fields as an additional project for the class. We saw
that non-comp majors overall found the class less interesting than those
pursuing COMP degrees, and they were somewhat interested (avg 4.39/7 on the
`interested_connections` score) in interdisciplinary connections with
programming. The only caveat is that we don't really have a way of knowing
whether adding an interdisciplinary, open-ended project would actually improve
student rating of course engagement, but I think it's a fair inference to make
based on the fairly high `interested_connections` score. I was also surprised
that those pursuing a COMP degree seemed more interested in this connection
than nonmajors, but in hindsight it makes sense; COMP majors would definitely
be interested in the intersection between COMP and other fields, but other
majors may not necessarily be interested in using COMP.