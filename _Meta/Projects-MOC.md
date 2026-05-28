---
type: moc
tags: [moc]
---

# 🎯 Mapa de Proyectos

[[_Meta/Home|🏠 Inicio]]

## 🟢 Activos
```dataview
TABLE WITHOUT ID
  file.link AS Proyecto,
  priority AS Prioridad,
  deadline AS Vencimiento,
  area AS Área
FROM "02_Projects"
WHERE status = "active"
SORT priority DESC, deadline ASC
```

## ⏸️ En pausa
```dataview
TABLE file.link AS Proyecto, deadline AS Vencimiento
FROM "02_Projects"
WHERE status = "paused"
```

## ✅ Completados (últimos 30 días)
```dataview
TABLE file.link AS Proyecto, file.mtime AS Cerrado
FROM "02_Projects"
WHERE status = "done"
  AND file.mtime >= date(today) - dur(30 days)
SORT file.mtime DESC
```

## 🗄️ Archivados
```dataview
LIST
FROM "05_Archive"
WHERE type = "project"
```
