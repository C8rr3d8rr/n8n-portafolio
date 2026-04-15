
<img width="1977" height="495" alt="Portada" src="https://github.com/user-attachments/assets/0c4e339b-3158-4439-99d7-0e038d48788d" />

# N8N-Telegram
Flujo de trabajo simple para un bot de telegram

<img width="1303" height="1010" alt="Telegram_Agendar_citas" src="https://github.com/user-attachments/assets/904a1cd1-86ac-419b-8b7c-8c8afff66b31" />



# **Como funciona:**

Este flujo implementa un agente básico de Telegram que permite interactuar automáticamente con los usuarios mediante mensajes. El proceso comienza cuando el bot recibe un mensaje desde Telegram, el cual es capturado por el flujo para ser procesado. A continuación, el sistema interpreta el contenido del mensaje y genera una respuesta utilizando la lógica configurada en el workflow. Finalmente, el agente envía una respuesta al usuario directamente en el chat de Telegram. Este flujo permite crear asistentes simples, automatizar respuestas o construir interfaces conversacionales básicas integradas con otros servicios y automatizaciones.

# **Caracteristicas principales:**

1. Recepción automática de mensajes
2. Generación automática de respuestas
3. Interacción en tiempo real
4. Integración con automatizaciones

# **Paso a paso:**

1. Nodo Receive a Message

Este nodo se encarga de recibir los mensajes enviados por los usuarios al bot de Telegram.
Cada vez que un usuario interactúa con el bot, el flujo captura el mensaje y lo envía al siguiente paso para su procesamiento.

2. Nodo AI Agent

En este paso se utiliza un agente de inteligencia artificial para interpretar el mensaje recibido y generar una respuesta.

El agente está configurado con:

Simple Memory, que permite mantener contexto básico dentro de la conversación.

Chat Model de Gemini, encargado de procesar el mensaje y generar una respuesta adecuada para el usuario.

Esto permite crear interacciones conversacionales automáticas dentro de Telegram.

3. Nodo Send Message

Finalmente, el flujo envía la respuesta generada por el agente de IA al usuario en Telegram, completando el ciclo de interacción y permitiendo mantener una conversación automática con el bot.

# **Integracion de herramientas**

1. Telegram

# **Claves API necesarias**

1. Telegram 
