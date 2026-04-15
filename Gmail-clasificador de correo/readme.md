<img width="1977" height="495" alt="Portada" src="https://github.com/user-attachments/assets/1be26de7-5b5d-44da-b886-88480c5d3fab" />

# N8N-Clasificador de correos
Flujo de trabajo para clasificar correos en carpetas especificas de correo electronico

<img width="1150" height="1032" alt="Clasificador_correos" src="https://github.com/user-attachments/assets/2517ac75-c58a-4e6d-bc86-a3ca23423856" />


## **Cómo funciona:**

Este flujo automatiza la gestión de correos electrónicos entrantes al procesar y clasificar automáticamente los mensajes que llegan a la bandeja de entrada. Cuando se recibe un nuevo correo, el sistema analiza su contenido y, mediante una lógica de clasificación previamente definida, identifica el nivel de interés o la intención del remitente. Con base en esta clasificación, el flujo organiza el correo archivándolo o asignándolo a la etiqueta o carpeta correspondiente. Esta automatización permite mantener una bandeja de entrada más organizada, priorizar conversaciones relevantes y optimizar la gestión del correo sin intervención manual.

## **Características principales:**

1. Clasificación automática de correos.
2. Organización inteligente de la bandeja de entrada.
3. Automatización sin intervención manual.
4. Priorización de conversaciones importantes.
5. Integración con n8n.
6. Escalable y personalizable.

## **Paso a paso:**

1. Nodo Get a Message

Este nodo se encarga de detectar los nuevos correos que llegan a la bandeja de entrada.
Aquí se configuran las credenciales de Gmail y la frecuencia de ejecución del flujo, definiendo cada cuánto tiempo el sistema revisará si existen nuevos mensajes para procesar.

2. Nodo Text Classifier

En este nodo se realiza el análisis y clasificación del contenido del correo.
Se conecta un modelo de chat o modelo de lenguaje que interpreta el texto del mensaje y determina la categoría correspondiente según la intención del remitente.
Adicionalmente, se definen las carpetas o etiquetas de destino a las que se enviarán los correos.

Nota: estas etiquetas o carpetas deben estar previamente creadas en Gmail.

3. Nodo Add Label to Message

Una vez clasificado el correo, este nodo asigna automáticamente la etiqueta correspondiente al mensaje, enviándolo a la carpeta definida según su categoría.

4. Nodo Remove Label from Message

Finalmente, este nodo elimina la etiqueta de la bandeja de entrada (Inbox), lo que provoca que el correo se archive automáticamente y quede únicamente en la carpeta asignada.
Esto permite mantener la bandeja de entrada limpia y organizada.

## **Integración de herramientas:**

1. Gmail

## **Claves API necesarias:**

1. API de GCP --> Gmail

