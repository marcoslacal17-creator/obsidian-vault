---
type: project
status: active
priority: medium
created: <% tp.date.now("YYYY-MM-DD") %>
deadline: 
area: 
tags: [project]
---

# <% tp.file.title %>

## 🎯 Objetivo
> Una frase clara del resultado esperado.

## 🧭 Contexto
Por qué este proyecto, para quién, qué cambia cuando se complete.

## 📋 Próximas acciones
- [ ] 

## 🗺️ Hitos
- [ ] 
- [ ] 

## 📝 Notas
- 

## 🔗 Recursos
- 

## 👥 Personas implicadas
- 

## 📅 Reuniones relacionadas
```dataview
LIST FROM "08_Meetings"
WHERE contains(project, this.file.link)
SORT date DESC
```

## ✅ Tareas
```tasks
not done
path includes {{ tp.file.path() }}
```

## 📜 Bitácora
- <% tp.date.now("YYYY-MM-DD") %>: proyecto creado
