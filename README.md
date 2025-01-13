## **Introducción**


### *Contexto*
El análisis y la visualización de datos son componentes esenciales en sistemas de monitoreo ambiental, ya que permiten a los responsables de la gestión de recursos  comprender patrones, identificar problemas y tomar decisiones informadas. Este software es una solución diseñada para recibir datos de sensores conectados a sistemas de monitoreo de calidad del agua, almacenarlos de manera estructurada y ofrecer herramientas avanzadas para su análisis y visualización. Además, soportará la configuración de alertas automáticas, reportes históricos y la integración con otros sistemas a través de una API.

### *Objetivos del sistema*
- Proveer un entorno para recibir, procesar y almacenar datos de calidad del agua enviados por dispositivos remotos.
- Facilitar la visualización de los datos a través de gráficos interactivos, reportes personalizados y dashboards.
- Implementar alertas automáticas para notificar eventos críticos relacionados con los parámetros medidos.

### *Proposito del documento*
El propósito de este documento es definir las especificaciones de requisitos para el desarrollo del servidor remoto destinado al análisis y visualización de datos de calidad del agua. El documento tiene como objetivos:
- **Describir las funcionalidades esperadas** del servidor, así como sus características técnicas.
- **Garantizar un entendimiento común** entre los desarrolladores y demás partes interesadas.
- **Proveer una guía clara** para el diseño, desarrollo, implementación y pruebas del servidor.
- **Establecer criterios de aceptación** para validar que el servidor cumpla con las necesidades del proyecto.

### *Descripción general de la aplicación*

#### **Visión del sistema**
El servidor remoto es una plataforma centralizada diseñada para gestionar los datos enviados desde dispositivos remotos de monitoreo de calidad del agua. Permitirá la recepción, almacenamiento y análisis de datos, y proporcionará a los usuarios finales herramientas para visualizar tendencias, generar reportes y recibir notificaciones en caso de anomalías.

#### **Componentes principales del sistema**
1. **Módulo de Recepción de Datos**
   - API REST de comunicación para recibir datos de los dispositivos remotos.
   - Validación y registro de datos recibidos para asegurar su integridad.

2. **Base de Datos**
   - Sistema de almacenamiento para manejar grandes volúmenes de datos de múltiples dispositivos.

3. **Módulo de Visualización y Análisis**
   - Dashboards interactivos para presentar datos.
   - Gráficos personalizados (líneas de tiempo, histogramas, comparaciones).
   - Filtros para segmentar datos por fechas, ubicaciones o tipos de sensores.

4. **Módulo de Notificaciones y Alertas**
   - Configuración de umbrales críticos para cada parámetro medido.
   - Generación automática de alertas enviadas por correo electrónico.

5. **Interfaz de Usuario (UI/UX)**
   - Portal web para usuarios finales con acceso a visualización de datos, alertas, y reportes.

6. **API de Integración**
   - Proveer acceso a los datos para aplicaciones externas mediante una API REST segura.

#### **Funciones clave del sistema**
- **Recepción de datos**: Captura y almacenamiento de datos enviados por los dispositivos de monitoreo.
- **Visualización interactiva**: Tableros que muestren valores actuales, históricos y tendencias de datos.
- **Reportes automatizados**: Generación de informes descargables en formatos como PDF y CSV.
- **Alertas en tiempo real**: Notificación de eventos críticos basados en umbrales definidos.

---

## **Especificaciones Técnicas**

### *Requisitos Funcionales*

1. **Recepción de Datos**
   - El servidor debe recibir los datos enviados por el sistema de monitoreo a través de un API REST.
   - Debe validar los datos recibidos para garantizar que estén completos y correctos antes de almacenarlos.

2. **Almacenamiento de Datos**
   - El servidor debe almacenar los datos de manera estructurada en una base de datos relacional.
   - Los datos deben incluir la información de:
     - Sensor (tipo y ubicación).
     - Valor medido.
     - Marca de tiempo.

3. **Gestión de Dispositivos**
   - Permitir la administración de dispositivos conectados, como registrar, actualizar y eliminar sistemas de monitoreo.
   - Cada dispositivo debe estar asociado a una ubicación específica y su estado de conexión debe ser monitoreado.

4. **Visualización de Datos**
   - Ofrecer gráficos interactivos para visualizar:
     - Tendencias de mediciones por sensor (líneas de tiempo, histogramas).
     - Comparaciones entre sensores o ubicaciones.
     - Mapas geográficos con puntos que indiquen las ubicaciones de los dispositivos y sus datos en tiempo real.
   - Permitir filtros por rango de fechas, sensores, ubicaciones o valores.

5. **Alertas y Notificaciones**
   - Generar alertas automáticas cuando los valores medidos excedan umbrales predefinidos.
   - Permitir que las alertas se envíen a través de correo electrónico.

6. **Configuración de Parámetros Globales**
   - Configurar los umbrales de alerta para cada tipo de sensor.
   - Definir la frecuencia de actualización de los datos en los dashboards.

7. **Reportes Automatizados**
   - Generar reportes periódicos (diarios, semanales, mensuales) que incluyan estadísticas, promedios, máximos y mínimos.
   - Permitir la descarga de reportes en formatos como PDF y CSV.

8. **API de Integración**
   - Ofrecer una API REST para que otros sistemas puedan acceder a los datos almacenados.
   - La API debe soportar autenticación y autorización para garantizar la seguridad.

### *Requisitos No Funcionales*
1. **Escalabilidad**
   - El servidor debe poder manejar datos provenientes de múltiples dispositivos simultáneamente.
   - Debe ser posible ampliar el almacenamiento y la capacidad de procesamiento según sea necesario.

2. **Disponibilidad**
   - El sistema debe estar disponible al menos el 99.5% del tiempo.  
   - Implementar redundancia para garantizar la continuidad del servicio en caso de fallos.

3. **Rendimiento**
   - El servidor debe procesar y almacenar los datos enviados con un retraso máximo de 2 segundos.
   - Los gráficos e informes deben cargarse en menos de 3 segundos para datos recientes.

4. **Seguridad**
   - Utilizar autenticación y autorización para acceder a la interfaz y la API.

5. **Interfaz de Usuario**
   - La interfaz debe ser accesible desde navegadores modernos y dispositivos móviles.
   - Diseñada con una experiencia de usuario (UX) intuitiva, incluso para usuarios no técnicos.

6. **Compatibilidad**
   - El servidor debe ser compatible con sistemas operativos estándar (e.g., Ubuntu Server, Windows Server).
   - Utilizar tecnologías ampliamente soportadas (e.g., PostgreSQL, MySQL, Node.js, Java, Python).

7. **Mantenimiento**
   - Permitir actualizaciones de software sin interrupciones significativas del servicio.
   - Proveer logs detallados para diagnóstico de errores y auditoría.

### *Pila tecnológica*

1. **Hardware**

| Descripción | Detalle |
| ------------- | -------------- |
| Servidor | - 2 procesadores de 16 nucleos
             - Memoria de 256 GB
             - Almacenamiento de 10 TB |

2. **Software**

| Descripción | Modelo/Versión |
| ------------- | -------------- |
| OpenJDK | 21 |
| Spring Boot | v3.4.1 |
| PostgreSQL | v16 |
| Node JS | v22.13 |
| React JS | v18.3.1 |

