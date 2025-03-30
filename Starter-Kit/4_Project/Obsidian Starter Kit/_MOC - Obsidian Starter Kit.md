---
view_count: 1
created: 2025-03-30, 16:01
modified: 2025-03-30, 18:11
tags:
  - type/structure
  - structure/moc
  - target/starterkit
aliases: 
lead: List of notes for an Obsidian Starter Kit published at GitHub.
template_type: Structure
template_version: "1.18"
---
<!--  See "Template Help" below for using properties -->

# MOC - Obsidian Starter Kit
<!--  Clear and descriptive title -->

<!--  Summarized structure from "lead"-key  in properties section -->

> [!Note]
> `= this.lead`

<!-- Main STRUCTURE of my content -->

<!-- Dataview table. Use as example and modify. -->

```dataview
TABLE 
	rows.file.link AS Note,
	rows.template_type AS Template,
	dateformat(rows.file.mday, "yyyy-LL-dd") AS Modified
FROM #target/starterkit 
FLATTEN file.folder
GROUP BY file.folder AS Folder
SORT Folder ASC
SORT Note ASC
```


---
# Back Matter

**Source**
<!-- Always keep a link to the source- --> 
- based_on:: [Example GROUP BY Queries - Dataview Example Vault](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Example%20GROUP%20BY%20Queries/)

**References**
<!-- Links to pages not referenced in the content. see: [[related note]] because <reason> -->
- see:: 

**Terms**
<!-- Links to definition pages. -->
- 

**Target**
<!-- Link to project note or externaly published content. -->
- used_in::

---
**Tasks**
<!-- What remains to be done with this note? --> 
- 

**Questions**
<!-- What remains for you to consider? --> 
- question::

---
**Template Help**
<!-- Links to external help pages on GitHub. -->
- [Basic Template Structure](https://github.com/groepl/Obsidian-Templates#basic-template-structure)
- [How to Use Links](https://github.com/groepl/Obsidian-Templates#how-to-use-links)
- [How to Use Tags](https://github.com/groepl/Obsidian-Templates#how-to-use-tags)
- [How to Search Notes](https://github.com/groepl/Obsidian-Templates#how-to-search-notes)
- [Plugins Needed](https://github.com/groepl/Obsidian-Templates#obsidian-plugins-needed)
- [Find Latest Updates](https://github.com/groepl/Obsidian-Templates)