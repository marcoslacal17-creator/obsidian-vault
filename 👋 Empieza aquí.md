---
type: guide
tags: [meta, onboarding]
---

# 👋 Bienvenido a tu vault

Esta vault está lista para usarse. Sigue estos pasos UNA VEZ.

## ✅ Paso 1 — Abrir esta carpeta en Obsidian
1. Abre Obsidian.
2. `Open folder as vault` → selecciona `C:\Users\marco\Documents\Obsidian\Vault`.

## ✅ Paso 2 — Instalar los plugins community
Settings → Community plugins → `Turn on community plugins` → Browse.

Instala estos en este orden (están en .obsidian/community-plugins.json):

1. **Templater** — templates dinámicos
2. **Dataview** — queries en notas (los dashboards lo usan)
3. **Periodic Notes** — daily/weekly/monthly
4. **Calendar** — sidebar
5. **Tasks** — sistema de tareas
6. **QuickAdd** — captura rápida
7. **Obsidian Git** — sync con GitHub
8. **Omnisearch** — búsqueda potente
9. **Advanced Tables** — tablas usables
10. **Excalidraw** — diagramas
11. **Iconize** — iconos en carpetas
12. **Style Settings** — UI para themes
13. **Linter** — formato auto
14. **Homepage** — abrir Home al iniciar
15. **Auto Link Title** — títulos al pegar URLs

## ✅ Paso 3 — Configurar plugins clave

### Templater
- Template folder: `09_Templates`
- Trigger Templater on new file: **on**
- Folder templates:
  - `00_Inbox` → (vacío, captura plana)
  - `02_Projects` → `09_Templates/Project`
  - `07_People` → `09_Templates/Person`
  - `08_Meetings` → `09_Templates/Meeting`
  - `06_Notes/Literature` → `09_Templates/Literature`
  - `06_Notes/Permanent` → `09_Templates/Permanent`
  - `03_Areas` → `09_Templates/Area`

### Periodic Notes
- Daily: folder `01_Daily`, template `09_Templates/Daily`
- Weekly: folder `01_Daily/Weekly`, template `09_Templates/Weekly`
- Monthly: folder `01_Daily/Monthly`, template `09_Templates/Monthly`

### Homepage
- Homepage note: `_Meta/Home`
- Open on startup: **on**

### Tasks
- Set done date on every completed task: **on**
- Auto-suggest: **on**

### Obsidian Git
- Auto-commit cada 10 min
- Auto-push: **on**
- Pull on startup: **on**

## ✅ Paso 4 — Conectar con GitHub (sync gratis)

1. Crea repo privado en GitHub llamado `obsidian-vault`.
2. **NO** lo inicialices con README (ya tienes uno).
3. Genera Personal Access Token: GitHub → Settings → Developer settings → Personal access tokens → **Fine-grained**, scope `Contents: Read/Write` sobre ese repo.
4. En PowerShell, dentro de la vault, ejecuta:
   ```powershell
   git remote add origin https://<TOKEN>@github.com/<TU_USUARIO>/obsidian-vault.git
   git branch -M main
   git push -u origin main
   ```
5. En plugin Obsidian Git → Authentication → pega el token.

## ✅ Paso 5 — Activa los CSS snippets
Settings → Appearance → CSS snippets → activa: `callouts`, `typography`, `focus`.

## ✅ Paso 6 — Tema recomendado
Settings → Appearance → Themes → Browse → **Minimal** (o **AnuPpuccin**).
Luego con plugin **Style Settings** lo afinas.

## 🚀 Cuando termines
- Abre [[_Meta/Home]] — tu dashboard.
- Crea tu primer daily con `Ctrl+P` → `Periodic Notes: Open today's daily note`.
- Captura cualquier idea en [[00_Inbox]] sin pensar dónde va. Luego la procesas.

---

**Borra este archivo cuando hayas completado el setup.** 🗑️
