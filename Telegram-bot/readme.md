<img width="1977" height="495" alt="Portada" src="https://github.com/user-attachments/assets/443bea38-4655-4b88-8609-36ea7185747b" />


# N8N-Telegram-BOT
Flujo de trabajo, en el cual podemos hacer el agendamiento de citas, cancelarlas, mirar la disponibilidad.

<img width="1303" height="1010" alt="Telegram_Agendar_citas" src="https://github.com/user-attachments/assets/9bc7546f-b2e9-46ce-8238-8c1ee95b7f59" />


# **Como funciona:** 

Este flujo implementa un bot de Telegram diseñado para gestionar citas de forma automatizada. A través del chat, los usuarios pueden agendar, cancelar o consultar sus citas de manera sencilla. Cuando se recibe una solicitud, el sistema interpreta la acción requerida y actualiza la información en una hoja de cálculo, donde se registran todas las citas. Dependiendo de la operación solicitada, el flujo puede crear nuevos registros, eliminar citas existentes o consultar las citas asociadas a un usuario. Además, el flujo se integra con Google Calendar para sincronizar las citas, permitiendo crear o eliminar eventos automáticamente. De esta manera, se mantiene una gestión centralizada y actualizada de las citas tanto en la hoja de cálculo como en el calendario.

# **Caracteristicas principales**

1. Gestión de citas desde Telegram
2. Registro automático en Google Sheets
3. Integración con Google Calendar
4. Automatización completa de operaciones

# **Paso a paso:**
1. Nodo Updates: Message

Este nodo se encarga de recibir los mensajes enviados por los usuarios al bot de Telegram.
Cada mensaje recibido inicia el flujo y permite identificar la acción que el usuario desea realizar.

2. Nodo Switch

El nodo Switch analiza el contenido del mensaje para determinar la acción solicitada por el usuario y dirige el flujo hacia el proceso correspondiente.

Las posibles acciones son:

2.1 Envío de mensaje inicial

En este camino se utiliza el nodo Send Message, donde se configura el bot para enviar una respuesta inicial o instrucciones al usuario sobre cómo interactuar con el sistema de citas.

2.2 Agendar cita

Cuando el usuario solicita agendar una cita, el flujo ejecuta los siguientes pasos:

Code: procesa la información enviada por el usuario, como fecha y hora solicitadas.

Get All: Events: consulta los eventos existentes en Google Calendar para verificar disponibilidad.

IF: valida si el horario solicitado está disponible.

Si la cita no está disponible:

Se envía una notificación informando al usuario que el horario no está disponible.

Si la cita está disponible:

Se agrega el registro en Google Sheets para mantener el control de citas.

Se envía una respuesta confirmando que la cita fue agendada correctamente.

3.2 Cancelar cita

Cuando el usuario solicita cancelar una cita, el flujo realiza el siguiente proceso:

Code: procesa la solicitud del usuario.

Get Many Events: consulta las citas existentes para identificar la que debe ser cancelada.

IF: verifica si la cita existe.

Si la cita no se encuentra:

Se envía un mensaje indicando que no se encontró una cita registrada.

Si la cita existe:

Se consulta la información en Google Sheets.

Se elimina el registro correspondiente mediante el nodo Delete Row or Columns from Sheet.

Finalmente, se envía un mensaje confirmando que la cita fue cancelada.

3.4 Consultar citas

Cuando el usuario desea consultar sus citas programadas, el flujo ejecuta:

Code: procesa la solicitud y los datos del usuario.

Read Sheets: consulta la hoja de cálculo donde están almacenadas las citas.

IF: verifica si existen citas registradas para ese usuario.

Si existen citas:

Se envía un mensaje con el detalle de las citas registradas.

Si no existen citas:

Se ejecuta un nodo Code para preparar la respuesta.

Se envía un mensaje indicando que no hay citas programadas.

# **Integracion de herramientas**

1. Telegram
2. Sheets
3. Google calendar

# **Claves API**

1. GCP --> Sheets
2. GCP --> Calendar
3. Telegram



