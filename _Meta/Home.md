---
type: dashboard
cssclasses: [dashboard]
---

# 🏠 Inicio

> Tu centro de mando. Bienvenido, Marco.

## 🚀 Accesos rápidos
- [[00_Inbox|📥 Bandeja]] · [[_Meta/Inbox-Triage|🧹 Procesar bandeja]]
- [[_Meta/Projects-MOC|🎯 Proyectos]] · [[_Meta/People-MOC|👥 Personas]]
- [[09_Templates|📐 Plantillas]]

## 📅 Hoy
```dataview
LIST
FROM "01_Daily"
WHERE file.name = dateformat(date(today), "yyyy-MM-dd")
```

## 🎯 Proyectos activos
```dataview
TABLE WITHOUT ID
  file.link AS Proyecto,
  status AS Estado,
  priority AS Prioridad,
  deadline AS Vencimiento
FROM "02_Projects"
WHERE status = "active"
SORT priority DESC, deadline ASC
```

## 🔥 Tareas urgentes
```tasks
not done
(due before in 7 days) OR (priority is high)
sort by due
limit 15
```

## 📥 Bandeja por procesar
```dataview
LIST
FROM "00_Inbox"
SORT file.cday DESC
LIMIT 10
```

## 🗓️ Próximas reuniones
```dataview
TABLE WITHOUT ID
  file.link AS Reunión,
  date AS Fecha,
  attendees AS Asistentes
FROM "08_Meetings"
WHERE date >= date(today)
SORT date ASC
LIMIT 5
```

## 📝 Notas recientes
```dataview
LIST
FROM "" 
WHERE !contains(file.path, "09_Templates")
  AND !contains(file.path, "_Meta")
SORT file.mtime DESC
LIMIT 10
```

## 📊 Estadísticas
```dataview
TABLE WITHOUT ID
  length(rows) AS Cantidad
FROM ""
WHERE !contains(file.path, ".obsidian")
GROUP BY type AS Tipo
SORT length(rows) DESC
```
