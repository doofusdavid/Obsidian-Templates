---
created: <% tp.file.creation_date() %>
---
# <% moment(tp.file.title,'YYYY-MM-DD').format("dddd, MMMM DD, YYYY") %>

<< [[00 - Daily/<% tp.date.now("YYYY", -1) %>/<% tp.date.now("MM-MMMM", -1) %>/<% tp.date.now("YYYY-MM-DD-dddd", -1) %>|Yesterday]] | [[00 - Daily/<% tp.date.now("YYYY", 1) %>/<% tp.date.now("MM-MMMM", 1) %>/<% tp.date.now("YYYY-MM-DD-dddd", 1) %>|Tomorrow]] >>

---
## ✅ Tasks
#### Due Today
```tasks
due today
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
## Morning Reflection 
- I'm grateful for: 
1. 
2. 
3. 
- Today's focus: 
- Positive affirmation:

## Today's Top 3 Priorities 
1. [ ] 
2. [ ] 
3. [ ] 

---
## 📆 Events

<%*

async function getDataFromAPI() {

const ignoredSubjects = ['Lunch'];

var ret = ''

try {
		const dateToRequest = tp.file.title;
		const lastDashIndex = dateToRequest.lastIndexOf("-");
		const formattedDate = dateToRequest.substr(0, lastDashIndex);
		console.log(formattedDate);
		const response = await fetch('https://hook.us1.make.com/4ma0teqjx1xckql4o2j69d4n4l75e7x7?date=' + formattedDate);
		const data = await response.json();
		console.log('returned data');
		console.log(data);
		const events = data.value;
		data.value.forEach(item => {
			if (!ignoredSubjects.includes(item.subject)) {
				const line = '### ' + item.subject;
				ret += line + "\n\n"; 
			}
		});
		

} catch (error) {
console.error(error);
}
return ret;
}
tR += await getDataFromAPI();

%>
---
## 📝 Notes
- <% tp.file.cursor() %>

## Evening Review
- Today's wins:
- Challenges faced:
- How I'll improve tomorrow:
- What I'm looking forward to:


---
### Notes created today
```dataview
List FROM "" WHERE file.cday = date("<%tp.date.now("YYYY-MM-DD")%>") SORT file.ctime asc
```

### Notes last touched today
```dataview
List FROM "" WHERE file.mday = date("<%tp.date.now("YYYY-MM-DD")%>") SORT file.mtime asc
```