<img width="1977" height="495" alt="Portada" src="https://github.com/user-attachments/assets/9c182782-c297-458c-a2e8-a9c5652f818a" />

# N8N-POSTGRES
Flujo para tomar informacion de un sheet de gmail para alojarlo en una tabla de postgres
<img width="1536" height="574" alt="image" src="https://github.com/user-attachments/assets/7899e213-3ad1-40af-8a6e-e048583f0829" />

## **Cómo funciona:**
Este flujo automatiza la extracción y transformación de datos provenientes de una hoja de cálculo para prepararlos y cargarlos en una base de datos PostgreSQL. El proceso comienza obteniendo la información almacenada en un Google Sheet, la cual es procesada y transformada para ajustarse a la estructura y formato requerido por la tabla de destino en PostgreSQL. Durante esta etapa, el flujo puede limpiar, reorganizar o adaptar los datos para garantizar su consistencia y compatibilidad con el esquema de la base de datos. Finalmente, la información transformada se inserta en la tabla correspondiente, permitiendo integrar datos de hojas de cálculo en sistemas de bases de datos de forma automática y estructurada.

## **Características principales:**

1. Extracción automática de datos desde Google Sheets
2. Transformación y adaptación de datos
3. Integración con bases de datos PostgreSQL
4. Automatización del proceso ETL

## **Paso a paso:**

1. Nodo Schedule Trigger

Este nodo inicia el flujo de manera automática según una frecuencia definida.
Permite programar cuándo se ejecutará el proceso (por ejemplo, cada hora, diariamente o en intervalos específicos) para revisar y procesar la información de la hoja de cálculo.

2. Nodo Read Sheet

En este paso, el flujo extrae los datos desde Google Sheets.
Se configuran las credenciales de acceso y se define la hoja específica desde donde se obtendrá la información que posteriormente será procesada.

3. Nodo Edit Fields

Este nodo se utiliza para seleccionar, reorganizar o modificar los campos provenientes de la hoja de cálculo.
Aquí se ajusta la estructura de los datos para que coincida con el formato esperado por el resto del flujo.

4. Nodo Code

En este paso se realiza la transformación lógica de los datos mediante código.
Se pueden aplicar procesos como limpieza de datos, formateo de valores, conversión de tipos de datos o preparación de la información para su posterior inserción en la base de datos.

5. Nodo AI Agent

Este nodo utiliza un agente de inteligencia artificial para interpretar o estructurar la información antes de enviarla a la base de datos.

En esta configuración se integran:

Chat Model de Gemini, que procesa o estructura los datos.

Tool de PostgreSQL, que permite ejecutar consultas o insertar registros directamente en la base de datos.

Esto permite automatizar la generación o adaptación de las consultas necesarias para almacenar la información correctamente.

6. Nodo Send Message

Finalmente, el flujo envía un mensaje de confirmación o notificación indicando que el proceso fue ejecutado.
Este mensaje puede utilizarse para informar sobre el resultado del flujo o confirmar que los datos fueron procesados correctamente.

## **Integración de herramientas:**

1. Gmail
2. Gemini
   
## **Claves API necesarias:**

1. API de GCP --> Gmail
2. API de gemini
