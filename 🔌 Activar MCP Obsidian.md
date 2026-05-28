---
type: guide
tags: [meta, mcp, claude]
---

# 🔌 MCP de Obsidian — configurado ✅

El MCP ya está conectado a Claude Code usando el **servidor MCP nativo** del plugin Local REST API v4.1.1 (sin wrapper Python).

## Cómo funciona

- Plugin **Local REST API with MCP** expone un servidor MCP HTTP en `https://127.0.0.1:27124/mcp/`
- Claude Code se conecta con la API key como Bearer token
- Mientras Obsidian esté abierto, Claude puede leer/escribir esta vault

## Requisitos en cada sesión

1. **Obsidian abierto**
2. **Plugin Local REST API activo** (toggle ON)
3. **HTTPS server habilitado** (puerto 27124, ya configurado)

## Capacidades de Claude

- Listar archivos por carpeta
- Leer cualquier nota
- Crear, editar, anexar notas
- Buscar texto en toda la vault
- Ejecutar comandos de Obsidian
- Acceder a metadata (frontmatter, tags, backlinks)

## Probarlo

En una nueva conversación de Claude Code, escribe:
> "lista las notas de mi vault de Obsidian"

Si responde con tus archivos → todo bien.
Si dice que no tiene MCP → reinicia Claude Code.

## Si pierdes la API key o quieres rotarla

1. Settings → Local REST API → **Reset all crypto** (botón rojo)
2. Vuelve arriba y copia la nueva key
3. PowerShell:
   ```powershell
   $s = "$env:USERPROFILE\.claude\settings.json"
   (Get-Content $s -Raw) -replace 'Bearer [a-f0-9]+', 'Bearer NUEVA_KEY' | Set-Content $s -Encoding utf8
   ```
4. Reinicia Claude Code

## Localización de la config

- **Claude Code**: `C:\Users\marco\.claude\settings.json`
- **Plugin REST API**: dentro de Obsidian, Settings → Community plugins → Local REST API
- **Servidor**: `https://127.0.0.1:27124` (HTTPS), endpoint MCP en `/mcp/`

---

**Borra este archivo cuando termines de verificar que funciona.** 🗑️
