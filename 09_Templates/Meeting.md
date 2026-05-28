<%*
const title = await tp.system.prompt("Título de la reunión");
const date = tp.date.now("YYYY-MM-DD");
await tp.file.rename(`${date} - ${title}`);
-%>
---
type: meeting
date: <% tp.date.now("YYYY-MM-DD") %>
time: <% tp.date.now("HH:mm") %>
attendees: []
project: 
tags: [meeting]
---

# <% tp.file.title %>

## 👥 Asistentes
- 

## 🎯 Objetivo
- 

## 📋 Agenda
1. 

## 📝 Notas
- 

## ✅ Action items
- [ ] 

## 🔗 Referencias
- 
