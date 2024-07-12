---
company: 
location: 
title: 
email: 
supervisor:
---
tags:: [[👥 People MOC]]

# [[<% tp.file.title %>]]
<% await tp.file.move("/People/" + tp.file.title) %>

## Notes
- 

## Meetings
```dataview
TABLE file.cday as Created, summary AS "Summary"
FROM "50 - Meeting Notes" where contains(file.outlinks, [[]])
SORT file.cday DESC
```