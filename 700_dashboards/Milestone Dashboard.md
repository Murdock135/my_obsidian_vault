# Personal Project and Discipline Milestones
## ongoing

## planned

## all
```dataview
task from "400_projects/410_personal_projects" OR "300_disciplines"
where contains(text, "#milestone")
```

# Professional Project Milestones

## ongoing
```dataview
task from "400_projects/420_professional_projects" or "400_projects/430_class_projects"
where contains(text, "#milestone")
where contains(text, "#ongoing")
```

## planned
```dataview
task from "400_projects/420_professional_projects"
where contains(text, "#milestone")
where contains(text, "#planned")
```

## all
```dataview
task from "400_projects/420_professional_projects" or "400_projects/430_class_projects"
where contains(text, "#milestone")
```
