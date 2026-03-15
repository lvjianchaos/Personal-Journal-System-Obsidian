---
created: 2026-03-16
updated: 2026-03-16
aliases:
tags:
source:
  - Ali Abdaal's Youtube video "How to Make Next Year The Best Year of Your Life"
  - https://www.youtube.com/watch?v=c_DOG_mXz5w
summary:
  - 这篇笔记包含了生命之轮背后的理论以及在obsidian上实现的相关代码
  - 我们使用这个图表来进行回顾
---

## 代码
### Wheel with auto-colors
```chart
type: polarArea
labels: [Soul, Career/Work, Love/Relationships, Health/Fitness, Personal Growth, Fun/Recreaction, Social, Finance]
series:
  - title:
	data: [8, 3, 6, 5, 4, 9, 2, 5]
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

### Wheel where you can specify the colors
```chart
type: polarArea
labels: [Soul, Career/Work, Love/Relationships, Health/Fitness, Personal Growth, Fun/Recreaction, Social, Finance]
series:
  - title:
	data: [8, 3, 6, 5, 4, 9, 2, 5]
	bacgroundColor: [
	  'rgba(255,99,132,0.2)',
	  'rgba(54,162,235,0.2)',
	  'rgba(255,206,86,0.2)',
	  'rgba(75,192,192,0.2)',
	  'rgba(153,102,255,0.2)',
	  'rgba(255,159,64,0.2)',
	  'rgba(199,199,199,0.2)',
	  'rgba(83,102,255,0.2)',	  
	]
	boderColor: [
	  'rgba(255,99,132,1)',
	  'rgba(54,162,235,1)',
	  'rgba(255,206,86,1)',
	  'rgba(75,192,192,1)',
	  'rgba(153,102,255,1)',
	  'rgba(255,159,64,1)',
	  'rgba(199,199,199,1)',
	  'rgba(83,102,255,1)',	  
	]
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
## 类别分解

1. **Soul (灵魂/精神)：**
     
    - **Focus：** 内心的平静、意义感、价值观、灵性成长。
    - **Activities：** 冥想、阅读哲学书籍、练习正念、反思人生。
    - **Example：** 每天花15分钟冥想，每周阅读一篇哲学文章，定期反思自己的价值观。
2. **Career/Work (事业/工作)：**
    
    - **Focus：** 职业满意度、工作成就感、职业发展、工作与生活的平衡。
    - **Activities：** 提升专业技能、寻找新的工作机会、与同事建立良好关系、设定职业目标。
    - **Example：** 参加行业培训课程，主动承担更具挑战性的工作任务，与导师交流职业规划。
3. **Love/Relationships (爱/人际关系)：**
    
    - **Focus：** ~~亲密关系~~、家庭关系、友谊、情感支持。
    - **Activities：** ~~与伴侣共度美好时光~~、与家人定期聚餐、与朋友保持联系、表达爱意和感激。
    - **Example：** ~~每周安排一次约会之夜~~，每天与家人分享彼此的生活，主动关心朋友的近况。
4. **Health/Fitness (健康/健身)：**
    
    - **Focus：** 身体健康、心理健康、能量水平、生活习惯。
    - **Activities：** 健康饮食、规律运动、充足睡眠、压力管理。
    - **Example：** 每天进行30分钟的运动，保持均衡的饮食，保证7-8小时的睡眠，学习放松技巧。
5. **Personal Growth (个人成长)：**
    
    - **Focus：** 学习新知识、提升技能、发展兴趣、自我完善。
    - **Activities：** 阅读书籍、参加课程、学习新技能、挑战自我。
    - **Example：** 每月阅读一本新书，学习一门新的语言，参加一个兴趣爱好小组。
6. **Fun/Recreation (乐趣/娱乐)：**
    
    - **Focus：** 享受生活、放松身心、释放压力、创造快乐。
    - **Activities：** 旅行、看电影、听音乐、参加派对、培养爱好。
    - **Example：** 每周安排一次娱乐活动，例如看电影、听音乐会，定期旅行放松身心。
7. **Social (社交)：**
    
    - **Focus：** 人际关系、社会互动、归属感、支持系统。
    - **Activities：** 与朋友聚会、参加社交活动、参与社区活动、加入俱乐部或团体、志愿服务。
    - **Example：** 每周与朋友聚餐，参加社区志愿者活动，加入一个兴趣爱好俱乐部。
8. **Finance (财务)：**
    
    - **Focus：** 财务安全、理财能力、财务目标、收入与支出。
    - **Activities：** 制定预算、储蓄、投资、学习理财知识。
    - **Example：** 制定每月预算，每月储蓄一定比例的收入，学习投资理财知识。