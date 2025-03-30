---
tags:
  - type/structure
  - structure/view
  - target/starterkit
aliases:
  - Analytics
created: 2023-04-08, 20:42
modified: 2025-03-30, 16:37
template_type: Structure
template_version: "1.4"
banner: "![[IMG_0319.png]]"
view_count: 3
---

[Home](Home.md) | [ARCO](ARCO%20View.md) | [Inspect](Inspect%20View.md) 
```dataviewjs 
// Select random quote or idea
let a = Math.random()

if (a < 0.5) {

dv.paragraph(">[!Quote]")

// List of quotes 
let quotes = []; 

// Extract quotes from pages
dv.pages("#theme/zettelkasten") 
	.where(page => page.quote) 	
	.forEach(page => { 
		dv.array(page.quote) 
			.forEach(quote => { quotes.push({ 
				message: (quote), 
				page: page }); 
	})}); 

// Select random quote
let text = quotes[Math.floor(Math.random() * quotes.length)] 

dv.paragraph("> " + text.message + " <br>- " 
	+ text.page.author + " <br><br><small>From: " 
	+ text.page.file.link) + "</small>"; 

} else {
 
 dv.paragraph(">[!Remember]-")
 // List of ideas 
 let ideas = []; 

 // Extract ideas from pages
 dv.pages("#theme/zettelkasten")
	.where(page => page.lead) 
	.forEach(page => { 
		dv.array(page.lead) 
			.forEach(lead => { ideas.push({ 
				message: (lead), 
				page: page }); 
	})}); 

 // Select random idea
 let text = ideas[Math.floor(Math.random() * ideas.length)] 

 dv.paragraph("> " +
 	"<b>" + text.page.file.name + "</b><br>" +
 	text.message + 
 	" <br><br><small>" + 
 	text.page.file.link +  " - " +
 	text.page.template_type  + ", " +
 	text.page.file.inlinks.length  + " inlinks, " +
 	text.page.file.outlinks.length  + " out, " +
 	text.page.file.etags.length  + " tags, " +
 	text.page.file.tasks.length  + " tasks, " +
 	moment(text.page.file.cday.toString()).format("DD.MM.YYYY") + "." +
 	"</small>"
 	);
 } 
 ```


```dataviewjs 

// --- Age ---
var first_note = "20220307";
var a = moment();
var b = moment(first_note);
var age_years = a.diff(b, 'years');
var age_month = a.diff(b, ',months');
var age_days = a.diff(b, ',days');
var age = a.diff(b, 'days') - 365 * age_years;
var test = moment.duration(age, "milliseconds").humanize();

var start = moment().startOf('day'); 
var dateformat = "YYYY-MM-DD, hh:mm";
start = moment(start).format(dateformat);

// --- Insights & Permanent Notes
var count_insights = dv.pages("#type/insight").length; 
var count_sketch = dv.pages('"3_Permanent" AND #type/sketchnote').length;  
var count_note = dv.pages('"3_Permanent" AND #type/note').length;  
var count_question = dv.pages('"3_Permanent" AND #type/question').length;  
var count_permanent = dv.pages('"3_Permanent"').length; 

// --- Modified Notes today

var count_modified_today = dv
		.pages('"3_Permanent"')
		.where(m => m.modified >= start)
		.length; 

var count_created_today = dv
		.pages('"3_Permanent"')
		.where(c => c.created >= start)
		.length; 
		
var today_modified = count_modified_today - count_created_today;

var icons = ""
if (today_modified >= 3){icons = "🍌"} 
if (today_modified == 2){icons = "🍏"} 
if (today_modified == 1){icons = "🍏🍏"}
if (today_modified <= 0){icons = "🍏🍏🍏"}

// === Count Permanent Notes ===
var count_notes = dv
	.pages('"3_Permanent"')
	.length;
	
// === Count Good Notes ===
var count_good_notes = dv
	.pages('"3_Permanent" AND !#type/term AND !#type/quote AND !#type/tool AND !#type/book')
	.where(y => y.modified != null) 
	.where(y => y.created != null)
	.where(y => y.lead != null && y.lead != "+++ Lead paragraph goes here +++")
	.where(y => y.file.outlinks.length != 0)
	.where(y => y.file.tags.length != 0)
	.where(y => y.file.tags.includes('#type'))
	.where(y => y.file.tags.includes('#theme'))
	.length;

var count_inspect = count_notes - count_good_notes;
var percentage_good_notes = (count_good_notes / count_notes * 100).toFixed(1);
var percentage_inspect = 100 - percentage_good_notes;

// === Days Viewed ===
var count_days_viewed_1 = dv
	.pages('"1_Fleeting"')
	.where(x => x.view_count != null) 
	.where(y => y.view_count > 0)  
	.length;

var count_days_viewed_2 = dv
	.pages('"2_Literature"')
	.where(x => x.view_count != null) 
	.where(y => y.view_count > 0)  
	.length;
	
var count_days_viewed_3 = dv
	.pages('"3_Permanent"')
	.where(x => x.view_count != null) 
	.where(y => y.view_count > 0)  
	.length;
	
var count_days_viewed_4 = dv
	.pages('"4_Project"')
	.where(x => x.view_count != null) 
	.where(y => y.view_count > 0) 
	.length;
	
var count_days_viewed_5 = dv
	.pages('"5_Structure"')
	.where(x => x.view_count != null) 
	.where(y => y.view_count > 0) 
	.length;

var count_days_viewed_total = count_days_viewed_1 + count_days_viewed_2 + count_days_viewed_3 + count_days_viewed_4 + count_days_viewed_5

// === Overflow ===
// === IN ===
var count_fleeting = dv.pages('"1_Fleeting"').length; 
var count_input = count_fleeting

var status_in = ""
if (count_input >= 10){status_in = "🔴"} 
if (count_input < 10){status_in = "🟡"} 
if (count_input < 8){status_in = "🟢"}

// === PERMANENT ===
// --- Count notes WITHOUT TIMESTAMP 
var count_timestamp = dv.pages('"3_Permanent"')
	.where(y => y.modified == null)
	.length;
// --- Count notes WITHOUT LEAD 
var count_lead = dv.pages('"3_Permanent"')
	.where(y => y.lead == null || y.lead == "+++ Lead paragraph goes here +++")
	.length;
// --- Count sketchnotes WITHOUT VISUAL 
var count_visual = dv.pages('#type/sketchnote')
	.where(y => y.visual == null || y.visual == "![[image.jpg]]")
	.length;

var count_perm = count_timestamp + count_lead + count_visual
var status_perm = ""
if (count_perm >= 250){status_perm = "🔴"} 
if (count_perm < 250){status_perm = "🟡"} 
if (count_perm < 225){status_perm = "🟢"}

// === OUT ===
var count_project_tasks = dv.pages('"4_Project"').file.tasks
	.where(c => !c.completed)
	.length;
var count_output = count_project_tasks

var status_out = ""
if (count_output >= 70){status_out = "🔴"} 
if (count_output < 70){status_out = "🟡"} 
if (count_output < 63){status_out = "🟢"}

// --- show results ---
dv.paragraph(">[!Data]")
dv.paragraph('<small> ' + 
	status_in + count_input + '/10' + 
	status_perm + count_perm + '/250' + 
	status_out + count_output + '/70 | ' + 
	icons + '[to eat](Inspect%20and%20Adapt%20-%20Dashboard.md) | ' + 
	age_years + ' years, ' + age + ' days | ' + 
	count_note + ' [notes](List%20of%20Notes.md) | ' + 
	count_sketch + '  [sketchnotes](List%20of%20Sketchnotes.md) | ' +  
	count_question + '  [questions](List%20of%20Questions.md) | ' +  
	count_insights + ' [[insights]] | ' + 
	percentage_good_notes + '% [good](Inspect%20Good%20Notes.md) | ' +
	count_days_viewed_total + ' [viewed](View%20Count%20-%20Unique%20Days%20Opened)' +
 	"</small>"
	);
```

<small>*) 100% organic thinking. Less than 5% AI-generated ideas.</small>

---
<!-- Main STRUCTURE of my content -->

**Workflow**
- [On This Day](On%20This%20Day.md) | [7 Days Created](7%20Days%20Created%20Chart.md) | [7 Days Modified](7%20Days%20Modified%20Chart.md) | [Maturity](Inspect%20Maturity%20Level.md)
- [Inspect and Adapt](Inspect%20and%20Adapt%20-%20Dashboard.md) 
- [[Best of|Best of]] - [[Zettelkasten Flowers 2024]]

**3_Permanent Notes**
- [[Permanent Notes - Days Viewed]]
- [[Permanent Notes - Created]]
- [Inspect Permanent Notes by type](Inspect%20Permanent%20Notes%20by%20type.md)
- [[Inspect Sources from Permanent Notes]]
- [[Permanent Notes without linked sources]] - based_on field
- [[Notes with SEE references]] - see field

**2_Literature Notes**
- [[Reference Notes - Days Viewed]]
- [Inspect Banners](Inspect%20Index%20Visuals.md) 

- [Reading](List%20of%20Reading.md) | [Books per Year](Reading%20List%20-%20Book%20per%20Year.md) | [[Bibliography]]

- [Books](Books.md) - [[Bibliography]]
- [List of Terms](List%20of%20Terms.md) - [[Glossary]] - [[List of Index]] - [[Index - Zettelkasten]] - [[Maps of Books]]
- [[Inspect Bibliographical Notes]]

**5_Structure Notes**
- [[Structure Notes - Days viewed]]

**6_Project Notes**
- [[Project Notes - Days viewed]]
- [[Project Notes - Created]]
-  [Inspect Project Notes](Inspect%20Project%20Notes.md)
- [[Project Notes without source links]]
- Posted in [[Forum Obsidian]] | [[Forum Zettelkasten]]

**Folders**
- [[Inspect Folder Usage]]

**Links**
- 

**Tags**
- [[Inspect Themes]]

**Keys & values**

**Other Analytics**
- [Wheel of Life](Wheel%20of%20Life%20-%20Related%20Ideas.md)
- [[PowerBI Analytics]]
- [List of Lists](List%20of%20Lists.md)  | [All notes](Dataview%20-%20All%20Notes.md) | [Views](List%20of%20Views.md)
- [Inspect Options](Inspect%20Options.md)
- [[List of Charts]] | [[List of Diagrams]]



**References**
<!-- Links to pages not referenced in the content. -->
- [Inspect Options](Inspect%20Options.md)

