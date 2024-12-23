

```dataview
TABLE WITHOUT ID
	file.link as "Project", status as "Status"
	from "400_projects" 
	where status
	sort status asc
```
