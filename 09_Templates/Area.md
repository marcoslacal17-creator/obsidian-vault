---
type: area
status: active
created: <% tp.date.now("YYYY-MM-DD") %>
tags: [area]
---

# <% tp.file.title %>

## 🎯 Estándar / definición
> Qué significa "estar bien" en esta área.

## 📊 Métricas / KPIs
- 

## 🎯 Objetivos actuales
- 

## 📋 Proyectos activos en esta área
```dataview
TABLE status, deadline, priority
FROM "02_Projects"
WHERE area = this.file.name
AND status = "active"
SORT priority DESC
```

## 📚 Recursos clave
- 

## 📝 Notas relevantes
```dataview
LIST
FROM "06_Notes"
WHERE contains(file.outlinks, this.file.link)
SORT file.mtime DESC
LIMIT 10
```

## 📜 Log de cambios
- <% tp.date.now("YYYY-MM-DD") %>: área creada
