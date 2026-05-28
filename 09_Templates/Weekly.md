<%*
const week = tp.date.now("YYYY-[W]ww");
await tp.file.rename(week);
-%>
---
type: weekly
week: <% tp.date.now("YYYY-[W]ww") %>
start: <% tp.date.weekday("YYYY-MM-DD", 1) %>
end: <% tp.date.weekday("YYYY-MM-DD", 7) %>
tags: [weekly, review]
---

# Semana <% tp.date.now("ww, YYYY") %>

[[_Meta/Home|🏠 Inicio]] | [[<% tp.date.now("YYYY-[W]ww", -7) %>|◀ Anterior]] | [[<% tp.date.now("YYYY-[W]ww", 7) %>|Siguiente ▶]]

## 🎯 Objetivos de la semana
- [ ] 
- [ ] 
- [ ] 

## ✅ Logros
- 

## 🚧 Bloqueos / problemas
- 

## 📚 Aprendizajes
- 

## 🔁 Hábitos
| Hábito | L | M | X | J | V | S | D |
|--------|---|---|---|---|---|---|---|
|        |   |   |   |   |   |   |   |

## 📅 Notas diarias de la semana
```dataview
LIST
FROM "01_Daily"
WHERE week = "<% tp.date.now("YYYY-[W]ww") %>"
SORT file.name ASC
```

## 🎯 Proyectos tocados
```dataview
TABLE status AS Estado, deadline AS Vencimiento
FROM "02_Projects"
WHERE contains(file.outlinks, this.file.link) OR contains(this.file.outlinks, file.link)
```

## ⏭️ Para la próxima semana
- 

## 🪞 Reflexión
**Qué funcionó:** 
**Qué no funcionó:** 
**Qué cambio:** 
