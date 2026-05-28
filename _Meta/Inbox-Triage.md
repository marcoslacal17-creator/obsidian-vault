---
type: dashboard
---

# 🧹 Procesar la Bandeja

[[_Meta/Home|🏠 Inicio]]

> Decide para cada nota: **archivar / proyecto / referencia / nota / borrar**.

## 📥 Bandeja actual
```dataview
TABLE WITHOUT ID
  file.link AS Nota,
  file.cday AS Capturada,
  length(file.outlinks) AS Enlaces
FROM "00_Inbox"
SORT file.cday ASC
```

## 📊 Edad de la bandeja
- **Hoy:** `$= dv.pages('"00_Inbox"').where(p => p.file.cday.toMillis() === dv.date("today").toMillis()).length`
- **Última semana:** `$= dv.pages('"00_Inbox"').where(p => p.file.cday >= dv.date("today").minus(dv.duration("7 days"))).length`
- **Más de 7 días sin procesar:** `$= dv.pages('"00_Inbox"').where(p => p.file.cday < dv.date("today").minus(dv.duration("7 days"))).length`

## 🚦 Flujo
1. Lee → 2. Decide destino → 3. Mueve a la carpeta correcta + añade `type` en el frontmatter.
