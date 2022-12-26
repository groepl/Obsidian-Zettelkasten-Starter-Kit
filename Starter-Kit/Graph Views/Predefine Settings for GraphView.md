---
tags: type/note type/tooltip tool/graphview 
#theme/ - build cluster 
#index/ - define entry point
# 
#type/ - how note looks like
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
created: 2022-11-19, 17:02
modified: 2022-11-19, 17:02
---

# Predefine Settings for GraphView

<!-- Main content of my thoughts really -->

**Predefined Settings for GraphView**
```dataviewjs 
const graph = app.internalPlugins.plugins.graph 
const settings = await graph.loadData() 
settings.colorGroups = [
	{ "query": "tag:type/sketchnote", "color": { "a": 1, "rgb": 16433473 } }, 
	{ "query": "tag:type/structure", "color": { "a": 1, "rgb": 11868672 } },
	{ "query": "tag:structure/mindmap", "color": { "a": 1, "rgb": 6724916 } } 
] 
await graph.saveData(settings) 
await graph.disable() 
await graph.enable() 
```

**Show Settings**
```dataviewjs 
const settings = await app.internalPlugins.plugins.graph.loadData() 
dv.el('pre', settings.colorGroups) 
```

- [Show GraphView Settings with JS](Show%20GraphView%20Settings%20with%20JS.md)

## How to use
To change between different groups profiles, you just need to launch the Javascript code above. 

You then could:

- Create a couple of different notes with the groups that you want, and just load one of the notes to change all your groups.
- Put the code in a Templater script and launch it from a hotkey.
- Or one of the many other plugins which let you run arbitrary Javascript in Obsidian.


---
## Questions
<!-- What remains for you to consider? --> 

Is there also an option to restore my filter settings in Graph View?
https://forum.obsidian.md/t/prevent-loosing-groups-in-graph-view-by-accident/46953/2

## Terms
<!-- Links to definition pages -->
- .

## References
<!-- Links to pages not referenced in the content -->

https://forum.obsidian.md/t/design-talk-about-the-graph-view/22594/56

https://forum.obsidian.md/t/design-talk-about-the-graph-view/22594/57

Graph View presets to save and load filters
https://forum.obsidian.md/t/graph-view-presets-to-save-and-load-filters-display-settings/8131

More:
https://forum.obsidian.md/t/automatically-graph-color/42978