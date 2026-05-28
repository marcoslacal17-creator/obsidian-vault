---
type: guide
tags: [meta, mcp, claude]
---

# 🔌 Activar MCP de Obsidian — pasos finales

He instalado todo lo necesario para que Claude (en futuras conversaciones) pueda leer y escribir directamente en esta vault sin que tengas que copiar y pegar nada.

Faltan 3 pasos rápidos que solo tú puedes hacer:

---

## ✅ Paso 1 — Activar el plugin Local REST API

1. `Settings` (engranaje abajo a la izquierda)
2. **Community plugins** → busca **Local REST API** en la lista
3. Si NO está activo, enciende el toggle
4. Acepta "Trust author" si te lo pide

---

## ✅ Paso 2 — Obtener la API Key

1. `Settings` → busca **Local REST API** en la barra lateral (sección "Community plugin settings")
2. Verás un campo **API Key** con un texto largo tipo `a1b2c3d4...`
3. Clic en el botón **Copy** que está al lado
4. **Guárdala en un sitio seguro** (la vas a usar en el paso 3)
5. Asegúrate de que **Enable Encrypted (HTTPS) Server** esté **ON** en el puerto **27124**

---

## ✅ Paso 3 — Pegar la API Key en Claude Code

Abre PowerShell y ejecuta (sustituyendo `TU_KEY_AQUI`):

```powershell
$settings = "$env:USERPROFILE\.claude\settings.json"
$content = Get-Content $settings -Raw
$content = $content -replace 'PEGA_TU_API_KEY_AQUI', 'TU_KEY_AQUI'
Set-Content -Path $settings -Value $content -Encoding utf8
```

O abre `C:\Users\marco\.claude\settings.json` con Notepad y reemplaza `PEGA_TU_API_KEY_AQUI` por la key copiada.

---

## ✅ Paso 4 — Probar que funciona

1. Cierra y vuelve a abrir Claude Code
2. En la próxima conversación, escribe: *"lista las notas de mi vault de Obsidian"*
3. Claude debería usar el MCP y responder con tus archivos

---

## 🛠️ Lo que el MCP te da

Cuando funcione, Claude podrá (sin que copies nada):
- **Leer** cualquier nota de tu vault por nombre o búsqueda
- **Crear** notas nuevas en cualquier carpeta
- **Modificar** notas existentes
- **Buscar** por texto completo en toda la vault
- **Listar** archivos por carpeta
- **Añadir** contenido a notas existentes
- **Ejecutar** comandos de Obsidian

Requisitos: Obsidian abierto + plugin Local REST API activo.

---

## 🐛 Si no funciona

- **Error "connection refused"** → Obsidian no está abierto o el plugin está apagado.
- **Error "401 unauthorized"** → la API key está mal pegada (sin espacios, sin comillas extras).
- **Error de certificado** → el plugin usa cert autofirmado, normal. mcp-obsidian lo ignora.
- **Claude no ve el MCP** → reinicia Claude Code (cierra y abre).

Si algo va mal, dímelo en chat y lo diagnostico.

---

**Borra este archivo cuando hayas terminado los 3 pasos.** 🗑️
