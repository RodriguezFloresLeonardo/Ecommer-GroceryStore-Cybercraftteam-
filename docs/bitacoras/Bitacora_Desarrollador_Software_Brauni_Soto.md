# BITÁCORA INDIVIDUAL DE TRABAJO
## Proyecto: GroStop — Plataforma E-Commerce de Abarrotes
Integrante: Brauni Alexander Soto Cordova
Rol Asignado: Desarrollador de Software / Full Stack
Stack Técnico: Python (Flask), MySQL, HTML5, CSS3 (Bootstrap), JavaScript
## 1. REGISTRO DE ACTIVIDADES Y CONFIGURACIÓN DEL ENTORNO
En el marco del análisis e implementación del proyecto GroStop, como Desarrollador de Software
asumí la responsabilidad de clonar la base del código, preparar el entorno de ejecución local, configurar la
persistencia de datos y realizar la evaluación técnica de la arquitectura web existente.
## 1.1 Exploración Inicial y Entorno de Desarrollo
Se realizó la clonación del repositorio original y el análisis de la estructura del proyecto. Se
procedió a la creación de un entorno virtual de Python (venv) para gestionar las dependencias de manera
aislada. Se identificaron los módulos requeridos, principalmente el microframework Flask, PyYAML para
la lectura de configuración y conectores de MySQL.
## 1.2 Registro de Incidencias: Gestión y Restauración de Base de Datos
Descripción del Problema: Al intentar levantar la aplicación por primera vez, el servidor Flask emitía
fallos críticos de conexión y no lograba interactuar con la base de datos.
Causa Raíz: Presenté dificultades iniciales con el componente de persistencia debido a que no había
investigado de forma suficiente el procedimiento adecuado para abrir, importar y administrar bases de
datos MySQL mediante archivos de volcado (Dump.sql) ni la configuración de parámetros en el archivo
database.yaml.
Solución Aplicada: Se realizó una investigación técnica sobre la sintaxis SQL de importación y el uso del
gestor de base de datos. Se creó manualmente el esquema online_store, se ejecutó la restauración del
script Dump.sql y se ajustaron las credenciales (usuario, contraseña y host) dentro de
database.yaml. Con esto se logró una conexión fluida y persistente entre la aplicación Flask y el
servidor MySQL.
## 2. EVALUACIÓN TÉCNICA DEL SISTEMA (PERSPECTIVA DE
DESARROLLADOR)
Desde la perspectiva de la ingeniería y desarrollo de software, el proyecto cumple de manera
satisfactoria con el objetivo académico de simular una plataforma de comercio electrónico funcional. No
obstante analizando el código fuente la maquetación y la arquitectura global se clasifica como un
Bitácora de Desarrollador - Proyecto GroStop Página 1 de 2
## 2.1 ANÁLISIS CRÍTICO DEL PROYECTO
A. Frontend (HTML, CSS y Bootstrap)
Las vistas están desarrolladas mediante plantillas HTML renderizadas con el motor Jinja2 de Flask.
Si bien la interfaz de usuario es funcional para la navegación, el diseño visual es sumamente elemental y
rígido. Se hace uso de Bootstrap para estructurar componentes y maquetado básico, pero carece de
modularidad en estilos y presenta oportunidades de mejora en cuanto a adaptabilidad responsiva en
dispositivos móviles.
B. Arquitectura del Backend (Flask)
La lógica de negocio y el enrutamiento se encuentran concentrados principalmente en un solo
archivo principal (app.py). Aunque esta estructura facilita la comprensión rápida en proyectos pequeños,
rompe con los principios de diseño modular. Desde el punto de vista de desarrollo profesional, se requeriría
refactorizar el código utilizando Blueprints en Flask para separar las responsabilidades (autenticación,
gestión de productos, carrito de compras y panel administrativo).
C. Persistencia de Datos y Consultas SQL
Las operaciones de lectura y escritura a la base de datos se ejecutan mediante consultas SQL
empaquetadas directamente dentro de las funciones de ruta en Python. Aunque esto permite un control
directo de los datos, incrementa la rigidez del código. La implementación de un mapeador objeto-relacional
(ORM) como SQLAlchemy proporcionaría una capa de abstracción superior, previniendo riesgos de
inyección SQL y simplificando el mantenimiento.
D. Manejo de Excepciones y Validaciones
El control de errores e insumos por parte del usuario es mínimo. Un sistema de producción
requeriría validaciones robustas tanto en el cliente (JavaScript) como en el servidor, además de un manejo
centralizado de excepciones para evitar la interrupción imprevista del servidor ante datos inválidos.
3. CONCLUSIÓN
El proyecto GroStop constituye una base funcional adecuada para comprender el flujo integral de
una aplicación web. La resolución del inconveniente con la base de datos permitió afianzar el conocimiento
sobre la capa de persistencia. La evaluación técnica demuestra que el sistema cumple con las
especificaciones mínimas pero requiere refactorizaciones estructurales en caso de escalar hacia un entorno
profesional.
