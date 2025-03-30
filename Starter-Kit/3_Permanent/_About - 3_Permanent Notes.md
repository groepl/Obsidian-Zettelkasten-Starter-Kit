---
tags:
  - type/structure
  - theme/zettelkasten
  - structure/about
  - target/starterkit
aliases: 
lead: "**Permanent Notes** are processed, stand-alone insights that are linked meaningfully into the system. They transform fleeting ideas into structured knowledge that can be revisited and built upon. Use them for writing notes in your own words, linking them to related concepts, and making them reusable."
visual: "![[image.jpg]]"
created: 2024-07-28, 13:49
modified: 2025-03-30, 16:36
template_type: Structure
template_version: "1.14"
view_count: 2
---
<!--  See "Template Help" below for using properties -->

<!--  Clear and descriptive title -->

<!-- Visual or sketchnote if available -->

![[About - 3_Permanent Notes.canvas|About - 3_Permanent Notes]]
[[About - 1_Fleeting Notes|1_Fleeting]] | [[_About - 2_Literature Notes|2_Literature]] | [[_About - 3_Permanent Notes|3_Permanent]] | [[About - 4_Project Notes|4_Project]] | [[_About - 5_Structure Notes|5_Structure]]

<!--  Summarized structure from "lead"-key  in properties section -->

> [!Definition]
> `= this.lead`

> [!Simple Rules]
>- Be extremely selective in what you decide to keep.
>- Use unique and descriptive titles.
>- Use your own words.
>- Don't mix multiple ideas in one note.
>- One idea, one note.
>- Summarize the main idea of the note in three sentences or less.
>- Leave a reason to revisit your idea.
>- Always keep a link to the source.

<!-- Main STRUCTURE of my content -->
```dataview
TABLE WITHOUT ID 
	file.link as "3_Permanent Notes", 
	(date(today) - file.cday).day as "alive",
	view_count AS "opened"
FROM "3_Permanent"
SORT file.cday desc
LIMIT 20
```


---
More about: [[Permanent Notes]]


