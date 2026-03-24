<img width="1977" height="495" alt="Portada" src="https://github.com/user-attachments/assets/cec06188-b415-42d0-909d-4629b416ed33" />

# N8N-AWS-IAM-Usuarios-Inactivos
<img width="2158" height="561" alt="image" src="https://github.com/user-attachments/assets/6a33ebff-acec-4624-a9ce-42a8ce998887" />

## **Como funciona:**

Este flujo automatiza la auditoría de actividad de usuarios en AWS IAM al identificar cuentas que no han registrado actividad durante los últimos 90 días. El proceso comienza consultando la lista de usuarios de IAM y recopilando información sobre su último acceso. Posteriormente, el flujo analiza estos datos para detectar qué usuarios superan el umbral de inactividad establecido. Una vez identificados, la información se organiza en formato de tabla y se envía automáticamente por correo electrónico, facilitando la revisión periódica de cuentas inactivas y apoyando las prácticas de seguridad y gobernanza en la gestión de accesos dentro de AWS.

## **Caracteristicas principales:**

1. Monitoreo automático de usuarios IAM
2. Detección de inactividad prolongada
3. Reporte en formato de tabla
4. Notificación automática por correo electrónico

## **Paso a paso:**

1. Nodo Schedule Trigger

Este nodo inicia el flujo de forma automática según una frecuencia programada.
Permite ejecutar el proceso periódicamente (por ejemplo, una vez al día o a la semana) para revisar la actividad de los usuarios en AWS IAM.

2. Nodo Get All: Users

En este paso, el flujo obtiene la lista completa de usuarios registrados en AWS IAM, lo que permite analizar cada cuenta dentro del sistema.

3. Nodo Get: User + Custom HTTP Request

Este nodo recupera información detallada de cada usuario, incluyendo datos relacionados con su último acceso o actividad.
El Custom HTTP Request permite consultar información adicional desde la API de AWS para completar los datos necesarios para el análisis.

4. Nodo Filter

En este paso se filtran los datos obtenidos para identificar los usuarios que cumplen con la condición de análisis, enfocándose en aquellos que podrían presentar inactividad.

5. Nodo Switch

El nodo Switch permite evaluar diferentes condiciones dentro del flujo, separando los usuarios según criterios definidos (por ejemplo, usuarios activos vs. usuarios inactivos).

6. Nodo Code + No Operation

En esta etapa se realiza el procesamiento lógico de los datos mediante código.
El nodo No Operation (Do Nothing) se utiliza para mantener la estructura del flujo cuando ciertos registros no requieren acciones adicionales.

7. Nodo Edit Fields

Este nodo organiza y estructura los datos de los usuarios identificados, preparando la información que será incluida en el reporte final.

8. Nodo Code

En este paso se realiza un procesamiento adicional de los datos, como formatear la información o calcular el tiempo de inactividad para cada usuario.

9. Nodo Generate HTML Template

Aquí se genera un reporte en formato HTML, estructurado como una tabla que muestra claramente los usuarios que no han tenido actividad durante los últimos 90 días.

10. Nodo Send Message

Finalmente, el flujo envía automáticamente un correo electrónico con el reporte generado, permitiendo a los administradores revisar fácilmente las cuentas inactivas y tomar acciones de seguridad si es necesario.


## **Integracion con herramientas:**

1. AWS
2. Gmail

## **Claves API's necesarias:**

1. API de GCP --> Gmail
2. API DE AWS --> IAM
