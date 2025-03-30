---
tags:
  - structure/list
  - structure/index
  - type/dataview
  - type/project
  - target/starterkit
banner: "![[banner_books.jpg]]"
created: 2022-03-04, 19:32
modified: 2025-03-30, 16:57
template_type: Structure
view_count: 1
---
  
# Quotes
<!-- A list of quotes from famous author‘s  -->
[[Reference]] > [[Authors]] | [[Bibliography]] | [[Books]] | [[List of Index|Index]] | [[Glossary]] | [[Quotes]]

### Datastory
```dataview
TABLE WITHOUT ID
	author AS Author, 
	quote AS Quote, 
	file.link as File
FROM #type/quote and 
	#theme/datastory  
SORT author ASC
```

### Learning
```dataview
TABLE WITHOUT ID
	author AS Author, 
	quote AS Quote, 
	file.link as File
FROM #type/quote and 
	#theme/learning 
SORT author ASC
```

### Sketchnotes

```dataview
TABLE WITHOUT ID
	author AS Author, 
	quote AS Quote, 
	file.link as File
FROM #type/quote and 
	#theme/sketchnotes 
SORT author ASC
```

### Thinking

```dataview
TABLE WITHOUT ID
	author AS Author, 
	quote AS Quote, 
	file.link as File
FROM #type/quote and 
	#theme/thinking   
SORT author ASC
```

### Writing

```dataview
TABLE WITHOUT ID
	author AS Author, 
	quote AS Quote, 
	file.link as File
FROM #type/quote and 
	#theme/writing   
SORT author ASC
```

### Zettelkasten
```dataview
TABLE WITHOUT ID
	author AS Author, 
	quote AS Quote, 
	file.link as File
FROM #type/quote and 
	#theme/zettelkasten  
SORT author ASC
```




### Other Quotes

```dataview
TABLE WITHOUT ID
	author AS Author, 
	quote AS Quote,
	file.link AS File
FROM #type/quote and !#theme/sketchnotes and !#theme/zettelkasten AND !#theme/writing AND !#theme/datastory AND !#theme/thinking AND !#theme/learning
WHERE quote != empty
SORT author ASC
```

### Quotes without Author
```dataview
TABLE WITHOUT ID
	author AS Author, 
	quote AS Quote,
	file.link AS File
FROM #type/quote and 
	!#theme/sketchnotes AND
	!#theme/zettelkasten AND 
	!#theme/writing
WHERE quote = empty
SORT author ASC
```

## References
- _Photo by <a href="https://unsplash.com/@chuttersnap?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">CHUTTERSNAP</a> on <a href="https://unsplash.com/?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Unsplash</a>_
- Query with [[Obsidian Plugin - Dataview]] 
