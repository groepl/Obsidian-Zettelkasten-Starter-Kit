---
tags:
  - type/structure
  - structure/reference
  - structure/list
  - target/starterkit
aliases: 
lead: +++ Lead paragraph goes here +++
created: 2023-04-02, 09:30
modified: 2025-03-30, 17:44
template_type: Structure
template_version: "1.4"
banner: "![[banner_books.jpg]]"
view_count: 1
---

# Glossary

[[Reference]] > [[Authors]] | [[Bibliography]] | [[Books]] | [[Glossary]] | [[Quotes]]

<!-- DataView table, use example and modify -->
```dataview
TABLE WITHOUT ID
	file.link as Terms, 
	lead AS "Definitions",
	length(file.inlinks) as "In"
FROM #type/term OR #type/tool 
WHERE lead != empty
SORT file.name ASC
```

## Without definitions

<!-- DataView table, use example and modify -->
```dataview
TABLE WITHOUT ID
	file.link as Terms, 
	lead AS "Definitions",
	length(file.inlinks) as "In"
FROM #type/term OR #type/tool 
WHERE lead = empty
SORT length(file.inlinks) DESC
```

## Tools only

<!-- DataView table, use example and modify -->
```dataview
TABLE WITHOUT ID
	file.link as Terms, 
	lead AS "Definitions"
FROM #type/term AND #type/tool
SORT file.name ASC
```

## Zettelkasten

<!-- DataView table, use example and modify -->
```dataview
TABLE WITHOUT ID
	file.link as Terms, 
	lead AS "Definitions"
FROM #type/term AND #theme/zettelkasten 
SORT file.name ASC
```
<!-- Options 
TABLE WITHOUT ID
	file.folder AS ...
	file.link AS ...
	file.name AS ...
	file.etags AS ...

FROM #target/forumzettelkasten  : when using tags
FROM "Books"                                : when using folders
FROM ""                                          : when using all folders
FROM #status/open OR #status/wip

SORT created DESC
SORT file.name ASC

WHERE read = 2023
WHERE status = "open"
WHERE contains(file.name,"LernOS Zettelkasten")

---
More about: 
https://github.com/blacksmithgu/obsidian-dataview/blob/master/docs/docs/queries/query-types.md
https://github.com/blacksmithgu/obsidian-dataview/blob/master/docs/docs/queries/data-commands.md

Source: 
https://github.com/groepl/Obsidian-Templates
-->


---
## Questions
<!-- What remains for you to consider? --> 
- 


## Terms
<!-- Links to definition pages -->
- 


## References
<!-- Links to pages not referenced in the content -->
- [Glossary of Sketchnotes](Glossary%20of%20Sketchnotes.md)
- [Glossary of Zettelkasten](Glossary%20of%20Zettelkasten.md)
- [PKM Glossary](PKM%20Glossary.md)
- https://blacksmithgu.github.io/obsidian-dataview/queries/dql-js-inline/ for use with "Term Template"
- Photo by [Maksym Kaharlytskyi](https://unsplash.com/@qwitka?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) on [Unsplash](https://unsplash.com/photos/Q9y3LRuuxmg?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)


