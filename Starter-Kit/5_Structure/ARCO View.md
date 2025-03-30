---
tags:
  - type/structure
  - structure/view
  - target/starterkit
aliases: ARCO
lead: Based on Nick Milo’s ACE framework.
created: 2023-09-05, 16:04
modified: 2025-03-30, 16:36
template_type: Structure
template_version: "1.6"
banner: "![[IMG_0319.png]]"
banner_x: 0.5
view_count: 3
updated: 2024-10-23T17:47
---

[Home](Home.md) | [ARCO](ARCO%20View.md) |  [Inspect](Inspect%20View.md) 
<!-- Main STRUCTURE of my content -->
> [!map]- Atlas
> _Book of maps_
>
>[[Atlas]] > [[Work]] | [[Community]] | [[Family]] | [[Self]] 
> 

> [!reference]- Reference
> _Book of facts and external links_
>
> [[Reference]] > [Authors](Authors.md) | [Bibliography](Bibliography.md) | [Books](Books.md) | [Glossary](Glossary.md) | [Quotes](Quotes.md)

> [!calendar]- Calendar
> _Book of events_
>
>###### Meetings
>- [[Zettelkastenrunde - Mon]] | [WOL Troy - Fri](WOL%20Circle%202024.md)
>
>###### Bullet Journal
>
>- [2023](2023.md) | [2024](2024.md) | [[2025]]
>- [[Jan 2025]] | [[Feb 2025]] | [[Mar 2025]]
>- [[Bullet Journal Collections]]
>
>###### Objectives & Key Results
>- [[OKRs 2022]] | [[OKRs 2023]] | [[OKRs 2024]] | [[OKRs 2025]]
>
>###### Vision Board
>- [[Vision Board 2022]] | [Vision Board 2023](Vision%20Board%202023.md) | [[Vision Board 2024]]
>- [[Wishes 2022]] | 
>- [[Ideas List]] | 

> [!organizer]- Organizer
> _Book of tasks and projects_
>
> ###### Projects
> [_e1 - Make Useful Notes](_e1%20-%20Make%20Useful%20Notes.md) | [LinkedIn](LinkedIn%20Log.md)
> 
> ###### Tasks
> [Tasks](Tasks.md) |  [Tasks Open](Tasks%20Open.md) | [from E-book](Tasks%20from%20E-book.md) | [from Zettelkasten](Tasks%20-%20Zettelkasten.md) | [from Sketchnotes](Tasks%20-%20Sketchnotes.md)
> 
> ###### Kanban
> [Kanban Board](Kanban%20Board.md) | [Kanban Dashboard](Kanban%20Dashboard.canvas)
>
>> [!backlog]- Backlog
>>```dataview
>>TABLE WITHOUT ID
>>	file.link as note,
>>	file.cday AS "created", 
>>	file.folder AS "folder" 
>>FROM "" 
>>WHERE kanban = "backlog"
>>SORT file.folder ASC
>>```
>
>>[!todo]- ToDo
>>```dataview
>>TABLE WITHOUT ID
>>	file.link as note,
>>	file.cday AS "created", 
>>	file.folder AS "folder" 
>>FROM "" 
>>WHERE kanban = "todo"
>>SORT file.folder ASC
>>```
>
>>[!doing]+ Doing - _WIP Limit 3_
>>```dataview
>>TABLE WITHOUT ID
>>	file.link as note,
>>	file.cday AS "created", 
>>	file.folder AS "folder" 
>>FROM "" 
>>WHERE kanban = "doing"
>>SORT file.folder ASC
>>```
>
>>[!done]- Done
>>```dataview
>>TABLE WITHOUT ID
>>	file.link as note,
>>	file.mday AS "modified", 
>>	file.folder AS "folder" 
>>FROM "" 
>>WHERE kanban = "done"
>>SORT file.mday DESC
>>LIMIT 5
>>```
>

<small>*) 100% organic thinking. Less than 5% AI-generated ideas.</small>