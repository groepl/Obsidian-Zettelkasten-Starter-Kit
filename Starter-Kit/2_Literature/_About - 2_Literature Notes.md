---
view_count: 2
created: 2024-07-26, 20:42
modified: 2025-03-30, 16:07
tags:
  - type/structure
  - structure/about
  - target/starterkit
aliases: 
lead: "**Literature Notes** are summaries of sources with key takeaways. They extract useful insights from books, articles, or lectures. Use them for highlighting arguments, summarizing theories, and noting relevant passages."
visual: "![[image.jpg]]"
template_type: Structure
template_version: "1.14"
---
<!--  See "Template Help" below for using properties -->

<!--  Clear and descriptive title -->
![[About - 2_Literature Notes.canvas|About - 2_Literature Notes]]
[[About - 1_Fleeting Notes|1_Fleeting]] | [[_About - 2_Literature Notes|2_Literature]] | [[_About - 3_Permanent Notes|3_Permanent]] | [[About - 4_Project Notes|4_Project]] | [[_About - 5_Structure Notes|5_Structure]]

<!--  Summarized structure from "lead"-key  in properties section -->

> [!Definition]
> `= this.lead`

> [!Simple Rules]
>- Be extremely selective in what you decide to keep.
>- Write in the context of the source.
>- Always keep a link to the source.

<!-- Main STRUCTURE of my content -->
<!-- Dataview table. Use as example and modify. -->
```dataview
TABLE WITHOUT ID 
	file.link as "2_Literature Notes", 
	(date(today) - file.cday).day as "Days alive" 
FROM "2_Literature"
SORT file.cday asc 
LIMIT 20
```


---
More about: [[Literature Notes]]
