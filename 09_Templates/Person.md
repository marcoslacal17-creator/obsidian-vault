---
type: person
company: 
role: 
email: 
phone: 
linkedin: 
first_contact: <% tp.date.now("YYYY-MM-DD") %>
tags: [person]
---

# <% tp.file.title %>

## 📇 Info
- **Empresa:** 
- **Rol:** 
- **Cómo nos conocimos:** 

## 💡 Notas
- 

## 🎁 Intereses / contexto personal
- 

## 📅 Interacciones
```dataview
LIST FROM "08_Meetings"
WHERE contains(attendees, this.file.link)
SORT date DESC
```

## ✅ Pendientes con esta persona
```tasks
not done
description includes <% tp.file.title %>
```

## 🔗 Links
- 
