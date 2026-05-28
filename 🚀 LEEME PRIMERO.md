---
type: guide
tags: [meta, onboarding]
---

# 🚀 Estado de tu vault — Léeme primero

Casi todo está hecho. Lo que falta y lo que ya tienes:

---

## ✅ Hecho (no toques nada)

- [x] **Estructura** de carpetas (PARA + Zettelkasten + Meta)
- [x] **9 plantillas** Templater pre-configuradas (Diaria, Semanal, Mensual, Proyecto, Reunión, Persona, Literatura, Permanente, Área)
- [x] **4 dashboards** (Inicio, Mapa de Proyectos, Mapa de Personas, Procesar Bandeja)
- [x] **15 plugins community** instalados y activados
- [x] **Templater** con folder templates mapeados
- [x] **Periodic Notes** con daily/weekly/monthly funcionando
- [x] **Homepage** abre [[_Meta/Home|Inicio]] al arrancar
- [x] **Tasks** con done date + auto-suggest
- [x] **Obsidian Git** con auto-commit cada 10 min (falta conectar remoto)
- [x] **Linter** activo (no toca templates)
- [x] **Auto Link Title** trae títulos al pegar URLs
- [x] **Tema Minimal** instalado
- [x] **3 snippets CSS** activados (callouts, typography, focus)
- [x] **app.json** configurado (adjuntos a `10_Attachments`, nuevas notas a `00_Inbox`, spellcheck es+en)
- [x] **Git local** inicializado con 4 commits

---

## ⚠️ Lo único que falta — GitHub (5 min cuando puedas)

1. Abre PowerShell y ejecuta: `notepad C:\Users\marco\Documents\Obsidian\Vault\connect-github.ps1`
2. Lee las instrucciones de arriba (crear repo + token).
3. Edita las 2 variables (`GITHUB_USER` y `GITHUB_TOKEN`).
4. Guarda y ejecuta:
   ```powershell
   cd C:\Users\marco\Documents\Obsidian\Vault
   ./connect-github.ps1
   ```
5. **Borra el token del script** después (o el archivo entero).

---

## 🎮 Atajos imprescindibles

| Atajo | Acción |
|---|---|
| `Ctrl+P` | Paleta de comandos (todo se hace desde aquí) |
| `Ctrl+O` | Cambiar de nota rápido |
| `Ctrl+Shift+F` | Buscar en toda la vault (Omnisearch) |
| `Ctrl+N` | Nueva nota (cae en `00_Inbox`) |
| `Ctrl+Click` | Abrir nota en panel nuevo |
| `Alt+E` | Insertar template (Templater) |
| `Ctrl+L` / `Ctrl+R` | Ocultar/mostrar sidebars |

---

## 🚀 Empieza así

1. **Crea tu primer daily**: `Ctrl+P` → escribe "today" → `Periodic Notes: Open today's daily note`.
2. **Captura algo**: `Ctrl+N` → escribe cualquier idea suelta, se guarda en `00_Inbox`.
3. **Crea un proyecto**: nueva nota dentro de `02_Projects` → Templater aplicará la plantilla.
4. **Revisión semanal**: cada domingo, `Ctrl+P` → `Periodic Notes: Open this week's note`.

---

## 🆘 Si algo no funciona

- **Tablas vacías** en Inicio → normal, no hay datos todavía. Crea algunas notas.
- **Aparece código `dataview...`** en vez de tablas → Settings → Community plugins → activa Dataview.
- **Templates no se aplican** → Settings → Templater → revisa que "Trigger Templater on new file" esté ON.
- **"No results to show"** en Dataview → texto del plugin, no es bug. Significa tabla vacía.

---

**Cuando termines de configurar GitHub, borra este archivo.** 🗑️
