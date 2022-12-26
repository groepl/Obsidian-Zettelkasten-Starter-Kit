---
tags: type/chapter target/ebook
#theme/ - build cluster 
#index/ - define entry point
# 
#type/ - note characteristics
#source/ - where note comes from
#target/ - where note will go to
# 
#chart/ - from #type/chart 
#kanban/ - from #type/kanban
#role/ - from #type/person
#structure/ - from #type/structure
#visual/ - from #type/visual
#
aliases:
#
title_short: "Smart Sketchnotes"
chapter: "0.0"
version: "0.1"
status: draft
# status: draft, final
#
created: {{date}}, {{time}}
modified: {{date}}, {{time}}
#
template-type: Ebook
template-version: "1.0"
#
cc: "CC BY-SA 4.0"
legalcode: https://creativecommons.org/licenses/by-sa/4.0/legalcode
---

# {{Title}}
<!-- Main content of this chapter -->



---
## Questions
<!-- What remains for you to consider in the draft version? --> 
- 

## Tasks
<!-- What remains to be done do get the final version? --> 
- [ ] prepare final version 
- 

## Table of Content
<!-- Links to chapters from e-book -->

```dataview
TABLE WITHOUT ID
	chapter AS "",
	file.link AS Title,
	modified AS Modified,
	status AS Status
FROM #type/chapter
WHERE title_short = "Smart Sketchnotes"
SORT chapter ASC
```

## References
<!-- Links to pages not referenced in the content -->
- [eBook - Smart Sketchnotes](eBook%20-%20Smart%20Sketchnotes.md)












