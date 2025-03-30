---
view_count: 2
created: 2024-08-19, 13:37
modified: 2025-03-30, 16:36
tags:
  - type/structure
  - structure/canvas
  - target/starterkit
aliases: 
lead: "**Project Notes** are notes related to specific, time-bound projects, containing actionable tasks, research, and drafts. They keep temporary, goal-oriented information separate from permanent knowledge. Use them for managing research for an article, tracking progress on a book, or organizing materials for a presentation."
visual: "![[image.jpg]]"
template_type: Structure
template_version: "1.14"
---
<!--  See "Template Help" below for using properties -->

![[About - 4_Project Notes.canvas|About - 4_Project Notes]]
[[About - 1_Fleeting Notes|1_Fleeting]] | [[_About - 2_Literature Notes|2_Literature]] | [[_About - 3_Permanent Notes|3_Permanent]] | [[About - 4_Project Notes|4_Project]] | [[_About - 5_Structure Notes|5_Structure]]

<!-- Visual or sketchnote if available -->

<!--  Summarized structure from "lead"-key  in properties section -->

> [!Definition]
> `= this.lead`

> [!Simple Rules]
>- One project, one folder.
>- Always keep a link to the source.
>- Add a link to the target.

<!-- Main STRUCTURE of my content -->

---
[[Forum Obsidian]] | [[Forum Zettelkasten]] | [[About - 4_Project Notes|6_Project Notes]]

```dataview
TABLE WITHOUT ID 
	file.link as "5_Project Notes", 
	visual as Visual,
	target as target,
	(date(today) - file.cday).day as "Days alive" 
FROM "4_Project"
SORT file.cday desc
LIMIT 30
```

---
More about: [[Project Notes]]
