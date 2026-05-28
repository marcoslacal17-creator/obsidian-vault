---
type: moc
tags: [moc, people]
---

# 👥 Map of People

[[_Meta/Home|🏠]]

## Por empresa
```dataview
TABLE WITHOUT ID
  file.link AS Persona,
  role AS Rol,
  email AS Email
FROM "07_People"
GROUP BY company
SORT company ASC
```

## Contacto reciente
```dataview
TABLE file.link AS Persona, file.mtime AS "Última edición"
FROM "07_People"
SORT file.mtime DESC
LIMIT 10
```

## Sin actividad (>90 días)
```dataview
LIST
FROM "07_People"
WHERE file.mtime < date(today) - dur(90 days)
SORT file.mtime ASC
```
