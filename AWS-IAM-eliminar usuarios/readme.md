<img width="1977" height="495" alt="Portada" src="https://github.com/user-attachments/assets/851aab63-6194-4d89-b4a1-4fce6e94634b" />

# N8N-AWS-IAM-Crear-Eliminar-Usuarios
Fujo para manipular usuarios de IAM de AWS
<img width="1492" height="452" alt="image" src="https://github.com/user-attachments/assets/04c6b34f-f19d-4127-8c0c-d0de3c2f62fb" />

## **Como funciona:**

Este flujo automatiza la gestión de usuarios a partir de notificaciones recibidas por correo electrónico. Cuando llega un nuevo mensaje, el sistema analiza su contenido para identificar el tipo de solicitud incluida en la notificación. Con base en esta información, el flujo determina si la acción requerida es la creación o eliminación de un usuario y dirige el proceso por la ruta correspondiente dentro del workflow. Posteriormente, ejecuta la operación solicitada en el sistema o servicio configurado. Finalmente, una vez completada la acción, el flujo envía una notificación por correo electrónico confirmando el resultado del proceso, lo que permite mantener un registro claro y automatizado de las solicitudes gestionadas.

## **Caracteristicas principales:**

1. Procesamiento automático de notificaciones por correo
2. Identificación inteligente de acciones
3. Ejecución automática de operaciones
4. Confirmación y registro mediante correo electrónico

   
## **Paso a paso:**

1. Nodo Gmail Trigger

Este nodo inicia el flujo al detectar la llegada de un nuevo correo electrónico en la bandeja configurada.
Permite monitorear automáticamente las notificaciones que contienen solicitudes relacionadas con la gestión de usuarios.

2. Nodo Code

En este paso se realiza un procesamiento inicial del contenido del correo.
Aquí se extrae y estructura la información relevante del mensaje, como el tipo de solicitud o los datos del usuario que deben ser utilizados en las siguientes etapas del flujo.

3. Nodo Mode: Rules

Este nodo aplica un conjunto de reglas de decisión para interpretar la solicitud recibida.
Las reglas permiten identificar si la acción solicitada corresponde a crear un usuario o eliminar un usuario.

4. Nodo Create User / Delete User

Dependiendo del resultado de las reglas evaluadas, el flujo toma uno de los dos caminos:

Create User: ejecuta el proceso de creación de un nuevo usuario en el sistema correspondiente.

Delete User: realiza la eliminación del usuario especificado en la solicitud.

5. Nodo Code

En este paso se realiza un procesamiento adicional de la información, que puede incluir la validación de los resultados de la operación o la preparación del contenido para la notificación final.

6. Nodo Send Message

Finalmente, el flujo envía un correo electrónico de confirmación informando el resultado de la operación realizada, permitiendo mantener un registro claro de las solicitudes procesadas.

## **Integracion de heramientas:**

1. AWS
2. Gmail

## **Claves API's necesarias:**

1. API GCP --> Gmail
2. API AWS --> IAM
