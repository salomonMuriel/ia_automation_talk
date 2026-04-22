# AI Workshop Presentation Generator Prompt

**Instructions for the AI:** You are an expert presentation designer and copywriter. Your task is to generate a comprehensive, slide-by-slide presentation for a 3-hour highly practical workshop on Automation and AI. 

Read the context, constraints, and structure below, and output the slide deck text, including visual suggestions and speaker notes for each slide.

---

## 1. Workshop Context
* **Speaker:** Salomón (co-founder of Ignia, an educational company).
* **Audience:** 40 "traditional" Colombian entrepreneurs. Their businesses range from idea stage to 10,000 million COP/yearly revenue. Industries include physical products (fashion, food), boutique consultancies, and services. They are **NOT** technical. 
* **Format:** 3-hour hands-on build-along, including a 20-minute dinner break. The guided building sections must be taught **LITERALLY CLICK-BY-CLICK**.
* **Presentation Style (The Alt-Tab Method):** The speaker will project slides full-screen, and then Alt-Tab to the live software to build alongside the audience. 
* **Tech Stack:** Fillout (Frontend), n8n (Backend/Middleware), Notion (Database), OpenAI/Anthropic (AI).
* **Core Philosophy:** "La IA es el camino, no la meta" (AI is the path, not the goal).

## 2. Strict Copywriting Rules
* **Language:** Colombian Spanish. Use local vocabulary naturally (e.g., "computador", "celular").
* **Pronoun:** You MUST strictly use **"tú"** (never use "usted"). 
* **Tone:** Colloquial, relatable, and highly practical. 
* **Formatting:** Use short, punchy sentences. Start sections with aggressive, attention-grabbing hooks. Use emojis where it makes sense to break up text and add energy.
* **Slide Philosophy:** Keep on-slide text minimal (max 6-8 words if possible). Put the heavy explanation in the speaker notes.
* **Click-by-Click Rule:** For all "Construcción Guiada" slides, the speaker notes and visual suggestions MUST break down the action into micro-steps (e.g., "1. Haz clic en el botón '+'. 2. Escribe 'Webhook'. 3. Conecta tu cuenta.").
* **Speaker Cues:** 1. Include `[⏰ Marcador de tiempo: Minuto X]` at the start of each section's speaker notes.
    2. Use `🕹️ [ALT-TAB AL SOFTWARE LIVE]` in the speaker notes exactly when Salomón needs to switch from the slide to his browser.

---

## 3. Workshop Structure & Slide Requirements

Please generate the presentation following this exact flow. For each slide, provide:
- **Slide Title**
- **On-Slide Text (minimal, punchy)**
- **Visual Suggestion (what should be on the screen/diagram)**
- **Speaker Notes (Detailed script for Salomón)**

### Section 1: Intro & Demystifying the Tech (Minutes 0 - 20)
* **Slide 1: Title Slide.** Needs a strong, aggressive hook about stopping manual work. Mention "Ignia" subtly.
* **Slide 2: The Promise.** What they will walk away with today (A working AI automated system).
* **Slide 3: The Rules.** Log in to accounts now. Introduce the 3 "Co-pilots" (technical helpers). Do not split your screen; watch me, then Alt-Tab.
* **Slide 4: Cómo funcionan las apps realmente.** Frontend, Backend, Base de Datos usando Instagram y Nubank.
* **Slide 5: Los Mensajeros.** Explicar Gatillos y Acciones (Tubitos/Enchufes) usando WhatsApp.

### Section 2: Construcción Guiada #1 - El Tubo Principal (Minutes 20 - 60)
* **Slide 6: Build #1 Overview.** Fillout ➔ n8n ➔ Notion.
* **Slide 7: Paso 1 - La Memoria (Notion).** Clic a clic para duplicar el template "Lead Tracker". `🕹️ [ALT-TAB]`
* **Slide 8: Creando la Llave (Notion API Key).** Clic a clic: 1. Settings. 2. Connections -> Develop integrations. 3. New integration. 4. Copiar el Internal Integration Secret. `🕹️ [ALT-TAB]`
* **Slide 9: Abriendo la Puerta (Permisos de Notion).** ¡Paso crítico! Explicar que la llave no sirve si la puerta tiene seguro. Clic a clic: 1. Ir a la base de datos "Lead Tracker". 2. Clic en los 3 puntos (...). 3. Connections -> Connect to. 4. Buscar la integración creada y darle acceso. `🕹️ [ALT-TAB]`
* **Slide 10: Paso 2 - El Gatillo (n8n).** Clic a clic para configurar el nodo Webhook y darle "Listen for Test Event". `🕹️ [ALT-TAB]`
* **Slide 11: Conectando los Tubos.** Clic a clic para agregar el nodo de Notion en n8n y pegar la "Llave" (API Key) en las credenciales.
* **Slide 12: CHECKPOINT VISUAL.** Pausa obligatoria. Todos levantan la mano cuando vean la pantalla de espera de n8n y el nodo de Notion sin errores rojos. Los copilotos revisan.
* **Slide 13: Paso 3 - La Vitrina (Fillout).** Clic a clic para crear el form y pegar la URL del Webhook. `🕹️ [ALT-TAB]`
* **Slide 14: ¡Momento Aha!** Hacer submit y ver cómo los datos llegan solos a Notion.

### Section 3: Construcción Guiada #2 - El Conserje de IA (Minutes 60 - 95)
* **Slide 15: Inyectando el Cerebro.** Explicar que la IA es solo un nodo de acción. 
* **Slide 16: La Llave Maestra (API Key de OpenAI).** Explicar de dónde sacar la llave compartida (ej. documento de la clase) y cómo pegarla en las credenciales de OpenAI en n8n. Clic a clic. `🕹️ [ALT-TAB]`
* **Slide 17: El Prompt.** Mostrar el prompt en pantalla (Resumen, Prioridad, Borrador de respuesta). Dónde pegarlo exactamente.
* **Slide 18: CHECKPOINT VISUAL.** Revisar que el nodo OpenAI esté bien conectado.
* **Slide 19: Probando al Conserje.** Cada uno simula ser su peor cliente en el form para ver cómo la IA lo organiza.

### Section 4: El Descanso (Minutes 95 - 115)
* **Slide 20: ¡A Comer!** Un slide relajado de 20 minutos de pausa. Pedirles que discutan cómo usarían el conserje en su empresa real.

### Section 5: Construcción Guiada #3 - El Gatillo Inverso (Minutes 115 - 140)
* **Slide 21: La base de datos también habla.** Notion como gatillo. Clic a clic para configurar. `🕹️ [ALT-TAB]`
* **Slide 22: La Acción (Gmail).** Si Notion dice "Aprobado" ➔ n8n ➔ Enviar correo. Clic a clic para conectar cuenta de Google. `🕹️ [ALT-TAB]`
* **Slide 23: CHECKPOINT VISUAL.** Prueba final de envío del correo automatizado.

### Section 6: Construcción Autónoma - El Sandbox (Minutes 140 - 165)
* **Slide 24: Espacio libre.** Tiempo de explorar templates en n8n con términos estrictos: "Google Sheets to", "Shopify", "Draft email", "Instagram". (Los copilotos se dividen en zonas para ayudar).

### Section 7: El Cierre (Minutes 165 - 180)
* **Slide 25: Mira lo que construiste.** Manos fuera del teclado. Reconocer el logro técnico de pasar de 0 a IA.
* **Slide 26: La Filosofía.** "La IA es el camino, no la meta". Tu negocio no es hacer flujos de n8n, es vender más y vivir mejor.
* **Slide 27: El Micro-Compromiso.** Tarea: Mañana, automatiza solo una tarea aburrida de 15 minutos usando esto. Cierre e info de Ignia.

---
**Output Generation:** Please begin generating the slides now.
