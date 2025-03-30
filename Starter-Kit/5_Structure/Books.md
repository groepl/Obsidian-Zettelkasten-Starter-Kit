---
tags:
  - type/structure
  - structure/list
  - target/starterkit
banner: "![[banner_books.jpg]]"
created: 2022-03-04, 19:32
modified: 2025-03-30, 16:54
view_count: 1
template_type: Structure
---
  
# Books 
<!-- A list of books for further study or of works consulted by an author.  -->
[[Reference]] > [[Authors]] | [[Bibliography]] | [[Books]] | [[Glossary]] | [[Quotes]]

> [[Maps of Books]]

### Reading
```dataview 
TABLE WITHOUT ID
	bibliography AS "Books",
	file.link as Notes
From #type/book 
Where contains(status, "reading") 
SORT bibliography ASC
```  

### Bibliography Chicago 17th Style
```dataview
TABLE WITHOUT ID
	bibliography AS "Books",
	file.link as Notes
FROM #type/book
WHERE bibliography !=empty
SORT file.name ASC
```

### Sketchnote Books

```dataview
TABLE WITHOUT ID
	bibliography AS "Books",
	file.link as books
FROM #type/book and #theme/sketchnotes 
SORT file.name ASC
```

### Zettelkasten Books

```dataview
TABLE WITHOUT ID
	bibliography AS "Books",
	file.link as books
FROM #type/book and #theme/zettelkasten  
SORT file.name ASC
```

### Other Books

```dataview
TABLE WITHOUT ID
	file.link as books, 
	file.mday AS "modified", 
	file.folder AS "folder" 
FROM #type/book and !#theme/sketchnotes and !#theme/zettelkasten
SORT file.name ASC
```


___

- Chicago Manual of Style 17th edition (note)
- Search bibliography data: [https://zbib.org](https://zbib.org/)

Zotero Bib
https://zbib.org/2f8ce7173dee4e32a4efe1f6312395b6

28.03.2022
https://zbib.org/57974b2429a84839be10d1f03cf13681

Export options:
- Save to Zotero
- Download BibTeX
- Download RIS

___


##### References
- _Photo by <a href="https://unsplash.com/@chuttersnap?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">CHUTTERSNAP</a> on <a href="https://unsplash.com/?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Unsplash</a>_
- [List of Reading](List%20of%20Reading.md)

### Books by Incoming Links

```dataview
TABLE WITHOUT ID
	file.link as books, 
	length(file.inlinks) AS in,
	file.mday AS "modified", 
	file.folder AS "folder" 
FROM #type/book
SORT length(file.inlinks) DESC
```
