<%*
const titulo = await tp.system.prompt("Título de la reunión");
const fecha = tp.date.now("YYYY-MM-DD");
await tp.file.rename(`${fecha} - ${titulo}`);
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

## 📋 Orden del día
1. 

## 📝 Notas
- 

## ✅ Acciones a realizar
- [ ] 

## 🔗 Referencias
- 
