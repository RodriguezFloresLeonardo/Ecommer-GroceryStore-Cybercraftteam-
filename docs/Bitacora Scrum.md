# Bitácora General de Seguimiento (Sprint Scrum)
Proyecto: Transporte Express de Comida (TEC) — basado en GroStop 
Periodo del Sprint: 10 de septiembre al 6 de octubre de 2026 
Objetivo del Sprint: Configurar el entorno de desarrollo local, restaurar la base de datos, estructurar el repositorio del equipo, definir el concepto del negocio enfocado en la cafetería del TecNM campus Matehuala y aplicar una primera mejora visual al frontend


## 1. Resumen Diario de Actividades (Daily Standup por Fecha)
10 de septiembre de 2026:

Leonardo Rodríguez Flores: Realizó la reunión de equipo para coordinar la revisión del funcionamiento del programa y definir la distribución de actividades [cite: 1, además de iniciar con la evaluación de los requisitos funcionales y no funcionales del sistema.

12 de Septiembre de 2026:

Brauni Alexander Soto Córdova: Clonó el repositorio original, creó un entorno virtual de Python (venv) y resolvió las incidencias de conexión a la base de datos configurando el archivo database.yaml .
 
 Diego Rosas Vázquez: Realizó la instalación y ejecución local del sistema, solucionó errores de dependencias y elaboró el diagrama de casos de uso y de clases/entidades basado en el esquema SQL .
 
 Diego Fernández Mendoza: Puso en marcha los servicios de Apache y MySQL en XAMPP y documentó el proceso de importación del archivo de respaldo (Dump.sql) mediante phpMyAdmin para solucionar la ausencia de tablas como customer .

1 de octubre de 2026:
 
 Amaury Alí Tristán Córdova: Creó el repositorio en GitHub e integró a todos los integrantes , verificó el acceso por roles , propuso opciones de identidad de marca  y actualizó la interfaz visual (frontend) añadiendo un logotipo y un diseño más cómodo.
## 2. Product Backlog / Tablero de Tareas con Fechas (Sprint Board)
| Módulo / Área | Tarea o Requisito | Fecha de Registro | Estado | Responsable | Observaciones |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Infraestructura** | Configuración del entorno local (Flask y dependencias) | 27 de septiembre de 2026  | Completado | Brauni Soto | Se aislaron las dependencias en un entorno virtual (`venv`). |
| **Base de Datos** | Creación del esquema e importación del volcado SQL (`Dump.sql`) | 2 de octubre de 2026 | Completado | Brauni Soto, Diego Fernández, Diego Rosas | Se solucionó el error de la tabla `customer` faltante. |
| **Control de Versiones** | Creación del repositorio en GitHub e integración del equipo | 1 de octubre de 2026  | Completado | Amaury Tristán | Quedó pendiente concluir el archivo `README`. |
| **Modelado UML** | Diseño de casos de uso y diagrama de clases/entidades | 30 de septiembre de 2026 | Completado | Diego Rosas | Basado en las 15 tablas y la vista del sistema. |
| **Identidad y Marca** | Definición del concepto, nombre ("TEC") y logotipo | 29 de septiembre de 2026  | Completado | Amaury Tristán | Adoptado oficialmente como *Transporte Express de Comida*. |
| **Frontend / UI** | Mejora visual y adaptación del diseño en HTML/CSS y Bootstrap | 5 de octubre de 2026  | Completado | Amaury Tristán | Falta definir la paleta de colores oficial. |
## 3. Registro de Impedimentos y Soluciones con Fechas
Incidencia 1 (6 de octubre de 2026): Fallos críticos de conexión al levantar Flask por primera vez debido a parámetros incorrectos en database.yaml y base de datos vacía .
Solución aplicada: Creación manual del esquema, ajuste de credenciales del usuario root de XAMPP e importación correcta del archivo de respaldo .
Incidencia 2 (6 de octubre de 2026): Error al registrar usuarios nuevos porque la tabla customer no existía .
Solución aplicada: Se cargó el archivo .sql completo directamente desde phpMyAdmin .
## 4. Retrospectiva y Plan de Acción
Evaluación del Ciclo (6 de octubre de 2026): Se cumplió con la meta de levantar la aplicación localmente, entender la estructura de datos y definir el enfoque institucional del proyecto [cite: 1, 2, 3, 4, 5]. Se detectó la necesidad de refactorizar el código backend a futuro (modularización con Blueprints) .
Siguientes Pasos (Backlog para el próximo Sprint):
Definir la paleta oficial de colores de la marca y la lista de precios de la cafetería .
Finalizar la documentación en el README y adjuntar los diagramas UML en GitHub .
Reforzar las validaciones de seguridad en el inicio de sesión y definir las pasarelas de pago .
