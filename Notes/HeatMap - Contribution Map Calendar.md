---
created: 2026-03-16
updated: 2026-03-16
alias:
tags:
summary: How to get a heatmap calendar!
---

All of this is better explained in [[Prakash Joshi Pax]]'s YouTube video [Contribution Graph: The Easiest Way to Track Habits in Obsidian](https://youtu.be/qZg-sunWu5E?si=Gigeyn3UnUTt1xJC).

## Steps

1.  Download the [[Contribution Map Community Plugin]]
2.  Go to note where you want to add graph > CMD + P (to open command palette) > type "contribution map"
3.  Go through the steps!

## Graph 1
```contributionGraph
title: Sleep Hours
graphType: default
dateRangeValue: 1
dateRangeType: LATEST_YEAR
startOfWeek: 1
showCellRuleIndicators: true
titleStyle:
  textAlign: center
  fontSize: 19px
  fontWeight: bold
dataSource:
  type: PAGE
  value: '"Journal/01 Daily"'
  dateField:
    type: FILE_NAME
  filters: []
  countField:
    type: PAGE_PROPERTY
    value: log-sleep-hours
fillTheScreen: true
enableMainContainerShadow: true
cellStyleRules:
  - id: default_b
    color: "#f00508ff"
    min: "0.01"
    max: "4"
  - id: default_c
    color: "#f89c00ff"
    min: "4"
    max: 5
  - id: default_d
    color: "#71e195ff"
    min: 5
    max: "7"
  - id: default_e
    color: "#216e39"
    min: "7"
    max: "24"

```
```contributionGraph
title: Learn Hours
graphType: default
dateRangeValue: 180
dateRangeType: LATEST_DAYS
startOfWeek: 1
showCellRuleIndicators: true
titleStyle:
  textAlign: center
  fontSize: 19px
  fontWeight: bold
dataSource:
  type: PAGE
  value: '"Journal/01 Daily"'
  dateField:
    type: FILE_NAME
  countField:
    type: PAGE_PROPERTY
    value: log-learn-hours
fillTheScreen: true
enableMainContainerShadow: true
cellStyleRules:
  - id: default_b
    color: "#9be9a8"
    min: "0.01"
    max: "1"
  - id: default_c
    color: "#40c463"
    min: "1"
    max: "3"
  - id: default_d
    color: "#30a14e"
    min: "3"
    max: "6"
  - id: default_e
    color: "#216e39"
    min: "6"
    max: "24"

```

## Graph 2
```contributionGraph
title: Learn Hours
graphType: month-track
dateRangeValue: 6
dateRangeType: LATEST_MONTH
startOfWeek: 1
showCellRuleIndicators: true
titleStyle:
  textAlign: center
  fontSize: 19px
  fontWeight: bold
dataSource:
  type: PAGE
  value: ""
  dateField:
    type: FILE_NAME
  countField:
    type: PAGE_PROPERTY
    value: log-learn-hours
fillTheScreen: false
enableMainContainerShadow: true
cellStyleRules:
  - id: Ocean_a
    color: "#8dd1e2"
    min: "0.01"
    max: "1"
  - id: Ocean_b
    color: "#63a1be"
    min: "1"
    max: 3
  - id: Ocean_c
    color: "#376d93"
    min: 3
    max: "6"
  - id: Ocean_d
    color: "#012f60"
    min: "6"
    max: "249"

```
