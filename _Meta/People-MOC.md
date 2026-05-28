---
type: moc
tags: [moc, people]
---

# 👥 Mapa de Personas

[[_Meta/Home|🏠 Inicio]]

## Por empresa
```dataview
TABLE WITHOUT ID
  file.link AS Persona,
  role AS Rol,
  email AS Correo
FROM "07_People"
GROUP BY company AS Empresa
SORT company ASC
```

## Contacto reciente
```dataview
TABLE file.link AS Persona, file.mtime AS "Última edición"
FROM "07_People"
SORT file.mtime DESC
LIMIT 10
```

## Sin actividad (más de 90 días)
```dataview
LIST
FROM "07_People"
WHERE file.mtime < date(today) - dur(90 days)
SORT file.mtime ASC
```
