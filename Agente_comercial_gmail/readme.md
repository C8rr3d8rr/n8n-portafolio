<img width="1977" height="495" alt="Portada" src="https://github.com/user-attachments/assets/cdcc2999-a2c1-4ab6-a8eb-76cc9c5936c7" />

# Agente para el area comercial

<img width="706" height="387" alt="agene_ia_comercial" src="https://github.com/user-attachments/assets/4758dd41-97e7-4b41-a64b-a010addc625b" />


## **🚀 Cómo funciona:**

Este flujo implementa un Agente de Inteligencia Artificial conectado a datos de negocio en tiempo real, capaz de transformar preguntas en insights accionables.

El proceso inicia mediante un Webhook, que recibe solicitudes externas (por ejemplo, preguntas del equipo comercial o de analistas). Estas solicitudes son interpretadas por un AI Agent, que analiza la intención del usuario y decide cómo responder utilizando diferentes herramientas.

Durante la ejecución, el agente puede consultar una base de datos mediante SQL, apoyarse en memoria para mantener contexto de conversaciones y utilizar capacidades de razonamiento para generar respuestas más precisas.

Finalmente, el flujo envía una respuesta estructurada a través de un canal de mensajería, permitiendo entregar insights claros y accionables de forma automática.

Este enfoque permite convertir consultas de negocio en análisis automatizados sin necesidad de intervención manual o conocimiento técnico por parte del usuario final.


## **⚡ Características principales:**
- Recepción de solicitudes en tiempo real mediante Webhook
- Agente de IA con capacidad de interpretación de lenguaje natural
- Integración con bases de datos mediante consultas SQL dinámicas
- Uso de memoria para mantener contexto conversacional
- Generación de insights automáticos para negocio
- Integración con herramientas de mensajería (ej: Slack, Chat)


## **🔄 Paso a paso:**
1. Nodo Webhook

Este nodo actúa como punto de entrada del flujo. Recibe solicitudes externas en formato HTTP (por ejemplo, preguntas como: “¿Cuál es la rentabilidad del cliente X este mes?”), permitiendo activar el agente en tiempo real.

2. Nodo AI Agent

Este es el núcleo del flujo. Se encarga de interpretar la solicitud del usuario y decidir qué acciones tomar para generar una respuesta adecuada.

En este nodo se integran múltiples componentes:

Chat Model (Gemini)
Procesa el lenguaje natural y entiende la intención del usuario.
Memory (Simple Memory)
Permite mantener contexto entre interacciones, mejorando la coherencia de las respuestas.
SQL Tool (PostgreSQL)
Ejecuta consultas dinámicas sobre la base de datos para obtener información relevante.
Think Tool (Razonamiento)
Permite al agente estructurar mejor sus respuestas y tomar decisiones más precisas.

Gracias a esta combinación, el agente puede transformar preguntas complejas en consultas de datos y respuestas claras.

3. Nodo SQL (Tool)

Este componente permite al agente interactuar directamente con la base de datos.
Aquí se ejecutan consultas generadas dinámicamente según la necesidad del usuario, como:

Rentabilidad por cliente
Comportamiento de ventas
Análisis temporal

Esto convierte al flujo en un sistema de Business Intelligence automatizado.

4. Nodo Create a Message

En este paso final, el flujo envía la respuesta generada por el agente a un canal de comunicación (como Slack o chat interno).

El mensaje puede incluir:

Insights de negocio
Métricas clave
Explicaciones en lenguaje natural

## **🔗 Integración de herramientas:**
- n8n (orquestación del flujo)
- Google Gemini (modelo de lenguaje)
- PostgreSQL (base de datos)
- Webhooks (entrada de datos)
- Herramientas de mensajería (ej: Slack, Google Chat)

## **🔐 Claves API necesarias:**
- API de Google Gemini
- Credenciales de base de datos PostgreSQL
- Credenciales del sistema de mensajería (si aplica)

## **💡 Casos de uso:**
📊 Consulta de métricas de negocio en lenguaje natural
📈 Análisis de comportamiento de clientes
💰 Evaluación de rentabilidad en tiempo real
⚠️ Detección de anomalías o caídas en ingresos
🤖 Asistente inteligente para equipos comerciales


## **🎯 Valor del proyecto**

Este flujo demuestra cómo combinar automatización (n8n) + inteligencia artificial + datos para crear un sistema capaz de:

Convertir preguntas de negocio en decisiones basadas en datos, en segundos.


## **Flujo**

Nota: lo encontraras en la carpeta


