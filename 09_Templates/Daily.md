<%*
const today = tp.date.now("YYYY-MM-DD");
const yesterday = tp.date.now("YYYY-MM-DD", -1);
const tomorrow = tp.date.now("YYYY-MM-DD", 1);
await tp.file.rename(today);
-%>
---
type: daily
date: <% tp.date.now("YYYY-MM-DD") %>
week: <% tp.date.now("YYYY-[W]ww") %>
tags: [daily]
---

# <% tp.date.now("dddd, DD MMMM YYYY") %>

[[<% yesterday %>|◀ Ayer]] | [[<% tomorrow %>|Mañana ▶]] | [[_Meta/Home|🏠 Inicio]]

## Foco del día
- 

## Tareas
- [ ] 

## Reuniones
```dataview
LIST FROM "08_Meetings"
WHERE date = date("<% today %>")
```

## Notas rápidas
- 

## Captura del día (Bandeja)
```dataview
LIST FROM "00_Inbox"
WHERE file.cday = date("<% today %>")
```

## Diario personal
**Cómo me siento:** 
**Lo mejor del día:** 
**Qué aprendí:** 
**Qué mejorar:** 

## Tareas creadas hoy
```tasks
not done
created on <% today %>
```

## Tareas vencidas
```tasks
not done
due before today
```
