#  Sistema Inteligente de Búsqueda y Resumen Automático de Noticias usando n8n e IA


## Descripción

Este proyecto implementa un chatbot desarrollado en **n8n** que permite buscar noticias recientes desde **Telegram**.

El usuario envía un tema (por ejemplo: *Inteligencia Artificial*, *Tecnología* o *Deportes*). El flujo consulta noticias mediante **GNews**, utiliza **Groq (compound-mini)** para analizarlas y resumirlas, y responde automáticamente por Telegram con los títulos, resúmenes y enlaces más relevantes.

## Arquitectura

```text
Usuario
   │
Telegram
   │
Telegram Trigger
   │
Edit Fields
   │
HTTP Request (GNews API)
   │
Basic LLM Chain (Groq)
   │
Send Telegram Message
   │
Usuario
```

## Flujo del proyecto

![Flujo del proyecto](https://raw.githubusercontent.com/manuelah123/bot-telegram/main/image.png)

## Tecnologías

- n8n
- Telegram Bot API
- GNews API
- Groq (compound-mini)
- ngrok
- JSON

## Requisitos

- n8n instalado
- Node.js
- Cuenta de Telegram
- Bot creado con BotFather
- API Key de GNews
- API Key de Groq
- ngrok

## Configuración

### 1. Ejecutar n8n

```bash
n8n
```

Por defecto:

```text
http://localhost:5678
```

### 2. Configurar ngrok

```bash
ngrok http 5678
```

Obtendrás una URL como:

```text
https://xxxx.ngrok-free.app
```

Inicia n8n usando esa URL:

**CMD**

```cmd
set WEBHOOK_URL=https://xxxx.ngrok-free.app
n8n
```

**PowerShell**

```powershell
$env:WEBHOOK_URL="https://xxxx.ngrok-free.app"
n8n
```

### 3. Credenciales

#### Telegram

Crear una credencial **Telegram API** e ingresar el **Bot Token** generado con BotFather.

#### GNews

En el nodo HTTP Request reemplazar:

```text
YOUR_GNEWS_API_KEY
```

por tu API Key.

#### Groq

Crear una credencial **Groq API** y pegar la API Key.

## Importar el workflow

Importar:

```text
workflow/telegram-news-bot-workflow.json
```

Asignar las credenciales de Telegram y Groq y configurar la API Key de GNews.

## Ejemplo

Usuario:

```text
Inteligencia Artificial
```

Bot:

```text
📰 OpenAI presenta un nuevo modelo

Resumen:
...

🔗 https://...
```

## Estado

Proyecto académico y de portafolio. Requiere configurar credenciales antes de ejecutarse.

# Autor
**Manuela Henao Bedoya**

# Licencia
**Este proyecto está bajo la licencia MIT.**



