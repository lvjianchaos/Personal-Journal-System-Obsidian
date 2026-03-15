---
date: <% moment(tp.file.title,'YYYY-[Q]Q').startOf('quarter').add(0,'days').format("YYYY-MM-DD") %>
tags:
  - "#type/quarterly-note"
---

---
```calendar-nav
```
---

## Quarterly Prep

## Quarter
> [! picture]- Pictures
<%*
 // Extracting the year and quarter from the title
let titleParts = tp.file.title.split('-'); // Assuming the title format 'YYYY-QQ'
let year = titleParts[0];
let quarter = parseInt(titleParts[1].replace('Q', ''));
// Calculating the start and end dates of the specified quarter
let start_of_quarter = moment(year, 'YYYY').quarter(quarter).startOf('quarter');
let end_of_quarter = moment(year, 'YYYY').quarter(quarter).endOf('quarter');
let days_in_quarter = end_of_quarter.diff(start_of_quarter, 'days') + 1;
// Script for Templater
Array(days_in_quarter).fill(null).map((x, i) => {
	let currentDate = start_of_quarter.clone().add(i, 'days');
	return `> ![[${currentDate.format("YYYY-MM-DD[]#YYYY-MM-DD")}]]`;
}).forEach(line => tR += line + '\n');

%>

> [! highlight]- Stand-out Days
> ```dataview
TABLE aliases
WHERE aliases != null
AND length(aliases) >= 1
AND date >= date(<% moment(tp.file.title, 'YYYY-[Q]Q').startOf('quarter').add(0, 'days').format("YYYY-MM-DD") %>)
AND date <= date(<% moment(tp.file.title, 'YYYY-[Q]Q').startOf('quarter').add(3, 'months').add(-1, 'days').format("YYYY-MM-DD") %>)

> [! highlight]- Highlights!
> ```dataview
TASK
FROM ""
WHERE contains(text, "#log/highlight")
AND date >= date(<% moment(tp.file.title, 'YYYY-[Q]Q').startOf('quarter').add(0, 'days').format("YYYY-MM-DD") %>)
AND date <= date(<% moment(tp.file.title, 'YYYY-[Q]Q').startOf('quarter').add(3, 'months').add(-1, 'days').format("YYYY-MM-DD") %>)
GROUP BY file.name AS filename
SORT filename ASC

> [! Calendar]- Monthly Reviews
> ```dataview
TASK
WHERE contains(text, "#log/month-review")
AND date >= date(<% moment(tp.file.title, 'YYYY-[Q]Q').startOf('quarter').add(0, 'days').format("YYYY-MM-DD") %>)
AND date <= date(<% moment(tp.file.title, 'YYYY-[Q]Q').startOf('quarter').add(3, 'months').add(-1, 'days').format("YYYY-MM-DD") %>)
GROUP BY file.name AS filename
SORT filename ASC

---
- [ ] #log/quarter-review

---
## Wheel Of Life
```chart
type: polarArea
labels: [Soul, Career/Work, Love/Relationships, Health/Fitness, Personal Growth, Fun/Recreaction, Social, Finance]
series:
  - title:
	data: [5, 5, 5, 5, 5, 5, 5, 5]
tension: 0.2
width: 88%
labelColors: true
fill: true
beginAtZero: true
rMax: 10
bestFit: false
bestFitTitle: undefined
bestFitNumber: 0
legendPosition: right
```

### 8个维度的反思
- [.] **Soul**: 5 #log/quarterly-soul
	- 冥想，阅读书籍与亲近大自然，练习感恩

- [.]  **Career/Work**: 5 #log/quarterly-career
	- 实现职业生涯里程碑，获得新技能，工作表现，工作与生活平衡，人际网络与专业发展

- [.] **Love/Relationships**:5 #log/quarterly-relationships
	- 与友人共度美好时光，开放的沟通，解决冲突和共同活动

- [.] **Health/Fitness**: 5 #log/quarterly-health
	- 定期锻炼，均衡饮食，定期健康检查，睡眠充足和压力管理

- [.] **Personal Growth**: 5 #log/quarterly-personal-growth
	- 阅读，参加课程，学习新技能，设定个人目标，练习正念与自我反省

- [.] **Fun/Recreation**: 5 #log/quarterly-fun
	- 运动，旅行，从事爱好，看电影，玩游戏以及任何认为愉悦且放松的活动，如：散步

- [.] **Social**: 5 #log/quarterly-social
	- 与友人社交，参加社交活动，参与社区活动，加入俱乐部或小组以及志愿服务

- [.] **Finance**: 5 #log/quarterly-finance 
	- 预算，储蓄，投资，管理费用，财务规划及债务管理

---

## 统计
### 日历图
```tracker
searchType: frontmatter
searchTarget: log-day-rating,log-sleep-hours,log-learn-hours,log-healthy-eating
datasetName: Day-Rating, Sleep-Hours, Learn-Hours,Healthy-Eating
month:
	startWeekOn: 'Sun'
	threshold: 0.99,6.99,3.99,0.99
	color: green
	initMonth: <% moment(tp.file.title,'YYYY-[Q]Q').format('YYYY-MM') %>
	circleColorByValue: true
	todayRingColor: white
	selectedRingColor: white
```

### 均值
```tracker
searchType: frontmatter
searchTarget: log-day-rating,log-sleep-hours,log-learn-hours,log-healthy-eating
datasetName: log-day-rating,log-sleep-hours,log-learn-hours,log-healthy-eating
startDate: <% moment(tp.file.title,'YYYY-[Q]Q').startOf('quarter').add(0,'days').format("YYYY-MM-DD") %>
endDate: <% moment(tp.file.title,'YYYY-[Q]Q').startOf('quarter').add(3,'months').add(-1,'days').format("YYYY-MM-DD") %>
summary:
	template:
		" - Average Day Rating: {{average()}}
		\n - Average sleep hours: {{average(dataset(1))}}
		\n - Average learn hours: {{average(dataset(2))}}
		\n - Average Healthy Food rating: {{average(dataset(3))}}"
```