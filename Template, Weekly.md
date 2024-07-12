---
created: <% tp.file.creation_date() %>
---
# Week <% moment(tp.file.title, 'GGGG-[W]WW').format("WW, YYYY") %>  - Week Starting  <% moment(tp.file.title, 'GGGG-[W]WW').startOf('week').add(8, 'day').format("dddd MMMM D")%>

[[00 - Weekly/<% tp.date.now("YYYY",-1) %>/<% tp.date.now("MM-MMMM", -1) %>/<% moment(tp.file.title,'GGGG-[W]WW').subtract(1,'week').format("GGGG-[W]WW") %>|Previous Week]] - [[00 - Weekly/<% tp.date.now("YYYY",-1) %>/<% tp.date.now("MM-MMMM", -1) %>/<% moment(tp.file.title,'GGGG-[W]WW').add(1,'week').format("GGGG-[W]WW") %>|Next Week]]

---
## 🗓️ Week In Review
### What did I accomplish last week?
<% tp.file.cursor() %>

## 🎯 Weekly Intentions
### What are my top 3 priorities this week?
- [ ] 


## ✅ Tasks
#### Due Next Week
```tasks
due next week
not done
description regex does not match /^$/
```
#### Due this week
```tasks
due this week
not done
description regex does not match /^$/
```
#### No due date
```tasks
not done
no due date
description regex does not match /^$/
```

---
## 📝 Notes
- 

---
### Notes created today
```dataview
List FROM "" 
WHERE date(file.cday).weekyear = date(today).weekyear AND date(file.cday).week = date(today).week 
SORT file.ctime asc
```

### Notes last touched today
```dataview
List FROM "" 
WHERE date(file.mday).weekyear = date(today).weekyear AND date(file.mday).week = date(today).week 
SORT file.mtime asc
```