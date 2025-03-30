---
tags:
  - type/structure
  - structure/list
  - theme/zettelkasten
  - target/starterkit
aliases: 
lead: "**Structure Notes** are high-level notes that organize and connect related notes into a meaningful structure. They serve as _index hubs_ for clusters of notes, guiding navigation through related ideas. Use them for creating overviews of key topics, linking related concepts together, and mapping the relationships between ideas."
created: 2024-08-19, 13:36
modified: 2025-03-30, 16:36
template_type: Structure
template_version: "1.14"
view_count: 2
---
<!--  See "Template Help" below for using properties -->

![[About - 5_Structure Notes.canvas|About - 5_Structure Notes]]
[[About - 1_Fleeting Notes|1_Fleeting]] | [[_About - 2_Literature Notes|2_Literature]] | [[_About - 3_Permanent Notes|3_Permanent]] | [[About - 4_Project Notes|4_Project]] | [[_About - 5_Structure Notes|5_Structure]]

<!--  Summarized structure from "lead"-key  in properties section -->

> [!Definition]
> `= this.lead`



<!-- Main STRUCTURE of my content -->

```dataview
TABLE WITHOUT ID 
	file.link as "5_Structure Notes", 
	(date(today) - file.cday).day as "Days alive",
	view_count AS "opened"
FROM "5_Structure"
SORT file.cday desc
LIMIT 20
```

---
More about: [[Structure Notes]]

