---
type: dashboard
---

# 🧹 Triage del Inbox

[[_Meta/Home|🏠]]

> Decide para cada nota: **archivar / proyecto / referencia / nota / borrar**.

## 📥 Inbox actual
```dataview
TABLE WITHOUT ID
  file.link AS Nota,
  file.cday AS Capturada,
  length(file.outlinks) AS Links
FROM "00_Inbox"
SORT file.cday ASC
```

## 📊 Edad del inbox
- **Hoy:** `$= dv.pages('"00_Inbox"').where(p => p.file.cday.toMillis() === dv.date("today").toMillis()).length`
- **Última semana:** `$= dv.pages('"00_Inbox"').where(p => p.file.cday >= dv.date("today").minus(dv.duration("7 days"))).length`
- **>7 días sin procesar:** `$= dv.pages('"00_Inbox"').where(p => p.file.cday < dv.date("today").minus(dv.duration("7 days"))).length`

## 🚦 Flujo
1. Lee → 2. Decide destino → 3. Mueve carpeta + añade frontmatter type.
