---
tags:
  - type/structure
  - structure/list
  - chart/bar-chart
  - theme/zettelkasten
  - type/dataviewjs
  - target/starterkit
aliases: 
created: 2023-04-08, 18:19
modified: 2025-03-30, 16:54
template_type: Structure
template_version: "1.4"
cc: CC BY-SA 4.0
source: https://github.com/groepl/Obsidian-Templates
view_count: 2
---

# 7 Days - Created

| [7 Days - Created](7%20Days%20Created%20Chart.md) | [7 Days - Summary](7%20Days%20Created%20List.md) | [7 Days - Modified](7%20Days%20Modified%20Chart.md) | [7 Days - Table](7%20Days%20Table.md) |

<!-- Main STRUCTURE of my content -->

```dataviewjs 

// === 7 Days Chart ===

// --- Age ---
var first_note = "20220307";
var a = moment();
var b = moment(first_note);
var age_years = a.diff(b, 'years');
var age_month = a.diff(b, 'months');
var age_weeks = a.diff(b, 'weeks')
var age_days = a.diff(b, 'days');
var age = a.diff(b, 'days') - 365 * age_years;

// --- Last 7 Days ---
var a = moment().format("YYYY-MM-DD");

var b = moment().subtract(1, 'week');
b = moment(b).format("YYYY-MM-DD");

var c = moment().subtract(1, 'month');
c = moment(c).format("YYYY-MM-DD");

var d = moment().subtract(3, 'month');
d = moment(d).format("YYYY-MM-DD");

var e = moment().subtract(6, 'month');
e = moment(e).format("YYYY-MM-DD");

var f = moment().subtract(1, 'year');
f = moment(f).format("YYYY-MM-DD");

var g = moment().subtract(2, 'year');
g = moment(g).format("YYYY-MM-DD");

// —— Last 1 Week —-
var count_note_1w = dv
	.pages('"3_Permanent"')	
	.where (p => p.created >= b)
	.length;

// —— Last 1 Month —-
var count_note_1m = dv
	.pages('"3_Permanent"')	
	.where (p => p.created >= c)
	.length;
var count_note_1m_13 = count_note_1m / 52 * 12;
count_note_1m_13 = count_note_1m_13.toFixed(1);

// —— Last 3 Month —-
var count_note_3m = dv
	.pages('"3_Permanent"')	
	.where (p => p.created >= d)
	.length;
var count_note_3m_13 = count_note_3m / 13;
count_note_3m_13 = count_note_3m_13.toFixed(1);

// —— Last 6 Month —-
var count_note_6m = dv
	.pages('"3_Permanent"')	
	.where (p => p.created >= e)
	.length;
var count_note_6m_26 = count_note_6m / 26;
count_note_6m_26 = count_note_6m_26.toFixed(1);

// —— Last 1 Year —-
var count_note_1Y= dv
	.pages('"3_Permanent"')	
	.where (p => p.created >= f)
	.length;
var count_note_1Y_52 = count_note_1Y / 52;
count_note_1Y_52 = count_note_1Y_52.toFixed(1);

// —— Last 2 Years —-
var count_note_2Y= dv
	.pages('"3_Permanent"')	
	.where (p => p.created >= g)
	.length;
var count_note_2Y_104 = count_note_2Y / 104;
count_note_2Y_104 = count_note_2Y_104.toFixed(1);

// —- All Since Start
var count_note_all = dv
	.pages('"3_Permanent"')	
	.length;

var note_per_week = count_note_all / age_weeks;
note_per_week = note_per_week.toFixed(1);

// --- show results ---
dv.paragraph('###### Created per week till ' + a);

// --- Set Colors ---
const CHART_COLORS = {
	  red: '#B51A00',
	  orange: 'rgb(255, 159, 64)',
	  yellow: '#FAC141',
	  green: 'rgb(75, 192, 192)',
	  blue: '#417CFA',
	  black: '#000000',
	  grey: '#CCCCCC',
	  light_grey: '#DDDDDD',
	  ultralight_grey: '#EEEEEE',
	  dark_grey: '#AAAAAA',
	  white: '#FFFFFF'
	}

const NAMED_COLORS = [
	  CHART_COLORS.red,
	  CHART_COLORS.orange,
	  CHART_COLORS.yellow,
	  CHART_COLORS.green,
	  CHART_COLORS.blue,
	  CHART_COLORS.purple,
	  CHART_COLORS.grey,
	]

// --- Create Chart ---
const chartData = { 
	type: 'bar', 
	data: { 
		labels: [
			'1W', 
			'1M',
			'3M', 
			'6M',
			'1Y',
			'2Y',
			'ALL'], 
		datasets: [
			{
			label: 'y',
			data: [count_note_1w, count_note_1m_13, count_note_3m_13, 
					count_note_6m_26, count_note_1Y_52,
					count_note_2Y_104, note_per_week],
			backgroundColor: [
				CHART_COLORS.yellow, 
				CHART_COLORS.ultralight_grey, CHART_COLORS.light_grey, 
				CHART_COLORS.grey, CHART_COLORS.dark_grey, CHART_COLORS.black], 
			borderColor: CHART_COLORS.white, 
			borderWidth: 1
			}
		] 
	},
	options: {
		indexAxis: 'x',
        plugins: {
            title: {
                display: false,
                text: 'Custom Chart Title'
            },
            subtitle: {
                display: false,
                text: 'Custom Chart Subtitle'
            },
            legend: {
	            display: false,
                position: 'right'
            }
        }
    }

} 

window.renderChart(chartData, this.container)

```

###### Notes Created
<!-- DataView table, use example and modify -->
```dataview
LIST
lead + " " + file.cday + "."
FROM "3_Permanent"
Where file.cday >= date(today) - dur(7 day)
SORT file.cday DESC
```



<!-- Options 
TABLE WITHOUT ID
	file.folder AS ...
	file.link AS ...
	file.name AS ...
	file.etags AS ...
	file.cday AS Date

FROM #target/forumzettelkasten  : when using tags
FROM "Books"                                : when using folders
FROM ""                                          : when using all folders
FROM #status/open OR #status/wip

SORT created DESC
SORT file.name ASC

WHERE read = 2023
WHERE status = "open"
WHERE contains(file.name,"LernOS Zettelkasten")
WHERE sketchnote != empty

LIMIT 3

---
More about: 
https://github.com/blacksmithgu/obsidian-dataview/blob/master/docs/docs/queries/query-types.md
https://github.com/blacksmithgu/obsidian-dataview/blob/master/docs/docs/queries/data-commands.md

Source: 
https://github.com/groepl/Obsidian-Templates
-->



---
# Back Matter
## Questions
<!-- What remains for you to consider? --> 
- 


## Terms
<!-- Links to definition pages -->
- 


## References
<!-- Links to pages not referenced in the content -->
- [Obsidian Charts - Plugin](Obsidian%20Charts%20-%20Plugin.md)


