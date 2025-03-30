---
tags:
  - type/structure
  - structure/moc
  - structure/index
  - target/project
  - target/github
  - target/starterkit
aliases: 
created: 2023-11-21, 20:38
modified: 2025-03-30, 16:03
banner: "![[IMG_0319.png]]"
banner_x: 0.5
lead: Startpage for Zettelkasten. To be revised if necessary.
visual: "![[image.jpg]]"
template_type: Structure
template_version: "1.12"
view_count: 185
---

[Home](Home.md) | [ARCO](ARCO%20View.md) |  [Inspect](Inspect%20View.md) 

```dataviewjs 
// Select random quote or idea
let a = Math.random()

if (a < 0.5) {

dv.paragraph(">[!Quote]")

// List of quotes 
let quotes = []; 

// Extract quotes from pages
dv.pages() 
	.where(page => page.quote) 	.forEach(page => { 
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
 dv.pages('"3_Permanent" AND #theme/zettelkasten') 
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
<small>*) 100% organic thinking. Less than 5% AI-generated ideas.</small>
