Welcome to the Mathwiki! Choose an article on the left side to start learning.
## Recently modified notes
```dataview
TABLE WITHOUT ID
	link(file.path, file.folder + "/" + file.name) AS "Note",
	dateformat(file.mtime, "yyyy-MM-dd, HH:mm") AS "Last Modified"
FROM ""
WHERE file.mtime >= date(today) - dur(30 days)
AND file.name != this.file.name
	AND !contains(file.path, "z_attachments")
	AND !contains(file.path, "z_templates")
SORT file.mtime DESC
LIMIT 10
```