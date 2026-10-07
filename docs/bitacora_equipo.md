# Bitácora de Equipo

**Proyecto:** Transporte Express de Comida (TEC) — basado en la plataforma E-Commerce GroStop (Python/Flask + MySQL)

**Integrantes:** Leonardo Rodríguez Flores, Brauni Alexander Soto Córdova, Amaury Alí Tristán Córdova, Juan Diego Rosas Vazquez y Diego Fernandez Mendoza

**Periodo registrado:** 5 al 6 de octubre de 2026

---

## 1. Propósito de la bitácora

Esta bitácora concentra el trabajo realizado por el equipo, la distribución de responsabilidades, los problemas encontrados y sus soluciones, así como las decisiones y pendientes del proyecto. Integra las bitácoras individuales de cada integrante (Líder de Requisitos, Desarrollador y Tester) y el registro de las reuniones del equipo, con el fin de dar una visión clara del estado real del proyecto.

## 2. Descripción del proyecto

El proyecto parte de GroStop, una tienda en línea de abarrotes desarrollada con Python (Flask) para la parte web y una base de datos MySQL administrada con XAMPP (esquema `online_store`). El equipo decidió adaptarla para un público local: la comunidad del Tecnológico Nacional de México campus Matehuala, enfocándola a la venta en línea de productos de la cafetería del Tec, con la interfaz traducida en su mayoría al español.

Como parte de esta adaptación, la plataforma fue renombrada **"Transporte Express de Comida"**, cuyas siglas forman **TEC**.

## 3. Roles del equipo

| Integrante | Rol | Responsabilidades principales |
|---|---|---|
| Leonardo Rodríguez Flores | Líder de Proyecto / Líder de Requisitos / Analista de Sistemas / Desarrollador | Evaluar el cumplimiento de requisitos, identificar brechas y definir el plan de acción |
| Brauni Alexander Soto Córdova | Desarrollador de Software / Full Stack | Clonar el repositorio, preparar el entorno, restaurar la base de datos y evaluar la arquitectura |
| Amaury Alí Tristán Córdova | QA / Tester / Control de Versiones (Git) | Probar el sistema, administrar el repositorio, documentar hallazgos y proponer la identidad de marca |
| Diego Rosas Vazquez | Arquitecto y Modelado UML | Construye el diagrama en casos de uso y un diagrama de clases/entidades del sistema |
| Diego Fernandez | Analista de Datos/ percistencia / integración | Indentificxa las tablas, sus relaciones y qué puede hacer cada tipo de usuario según los permisos definidos |

**Stack técnico:** Python (Flask), MySQL (XAMPP / phpMyAdmin), HTML5, CSS3 (Bootstrap), JavaScript, Jinja2, PyYAML, Git y GitHub.

## 4. Registro cronológico de actividades

### 5 de octubre de 2026 — Reunión de equipo (registro: Leo)

- Se realizó una reunión para discutir las actividades restantes necesarias para la revisión y discusión sobre el funcionamiento del programa y cómo se ejecuta en la computadora de cada integrante.
- Se acordó la división de las actividades que corresponden a cada integrante.
- Los integrantes confirmaron la reunión y los acuerdos tomados.

### 6 de octubre de 2026 — Brauni

- Se creó la estructura base del proyecto.
- Se agregaron los diagramas de casos de uso y de la base de datos.

### 6 de octubre de 2026 — Amaury

- Se agregó un diseño moderno a la interfaz y se adjuntó un logotipo.
- Se asignó el nombre "Transporte Express de Comida" (TEC).
- El cliente ya puede ingresar a la plataforma de una manera más cómoda gracias a la nueva interfaz.
- **Pendiente:** realizar el commit de los cambios.

## 5. Resumen del trabajo por integrante

### 5.1 Desarrollo (Brauni)

- Clonación del repositorio original y análisis de la estructura del proyecto.
- Creación de un entorno virtual de Python (venv) para gestionar dependencias de forma aislada.
- Identificación de los módulos requeridos: Flask, PyYAML (lectura de configuración) y conectores de MySQL.
- Creación manual del esquema `online_store`, restauración del script `Dump.sql` y ajuste de credenciales (usuario, contraseña y host) en `database.yaml`.
- Evaluación técnica del sistema (ver sección 7).

### 5.2 Operación y despliegue

Se documentó la puesta en marcha del proyecto en una computadora local:

- Se encendieron los servicios de Apache y MySQL desde el panel de control de XAMPP.
- Se revisó que la base de datos `online_store` coincidiera con lo que requiere la página web.
- Se revisó `database.yaml`, verificando usuario y contraseña acordes al entorno local. En XAMPP el usuario por defecto es `root` y no lleva contraseña, por lo que se dejó la configuración de ese modo.
- Se instalaron las librerías de Python necesarias desde la terminal.
- Resultado: el sitio web levantó sin problemas en la dirección local del navegador.

### 5.3 Requisitos (Leonardo)

Se revisó el código y el repositorio para evaluar si la solución responde a las necesidades del negocio.

**Requisitos funcionales**

| Requisito | Estado | Hallazgo |
|---|---|---|
| Visualización y filtro del catálogo | Cumplido parcialmente | Existe la estructura básica por categoría; falta verificar paginación y búsqueda en tiempo real |
| Gestión del carrito de compras | Cumplido | Permite agregar, modificar cantidades y eliminar ítems antes del pago |
| Registro y autenticación de usuarios | Incompleto | Falta validar políticas de seguridad en credenciales y persistencia de sesiones; no se validan los correos |
| Procesamiento de pedidos (checkout) | Sin finalizar | La orden se registra, pero falta especificar las pasarelas de pago |

**Requisitos no funcionales**

- **Usabilidad y UX:** aceptable a medias; la navegación es directa para compras rápidas.
- **Trazabilidad y gestión de cambios:** excelente; el historial de commits en Git permite relacionar requisitos con cambios en el código.
- **Escalabilidad y rendimiento:** requiere pruebas de carga para evaluar la latencia ante picos de consulta.

**Brechas identificadas (Gap Analysis)**

- Validación de inventarios: falta el control de stock en tiempo real para evitar compras de productos agotados.
- Manejo de promociones: no está especificado el módulo de cupones o descuentos por volumen.
- Notificaciones de pedido: se requiere enviar confirmaciones por correo o mensajes de estado del envío.

### 5.4 Pruebas y control de versiones (Amaury)

| Área | Qué se hizo | Resultado |
|---|---|---|
| Concepto del proyecto | Se revisó con el equipo qué va a vender la página | Claro: venta en línea de productos de la cafetería del Tec |
| Identidad de la página | Se verificó si existía nombre, marca y colores | Nombre y logotipo definidos el 6/10; la paleta de colores sigue pendiente |
| Repositorio en GitHub | Se creó y se incluyó a todos los integrantes | Exitoso; falta agregar el UML y terminar el README |
| Pantallas del sistema | Se probó el acceso como Cliente y como Administrador | Se puede abrir en ambos roles; faltan funciones para cada usuario |

## 6. Incidencias y soluciones

| # | Incidencia | Causa | Solución |
|---|---|---|---|
| 1 | Al levantar Flask por primera vez, errores críticos de conexión con la base de datos | Falta de conocimiento del procedimiento para importar bases de datos MySQL mediante archivos de volcado (`Dump.sql`) y de la configuración de `database.yaml` | Investigación sobre la sintaxis SQL de importación, creación manual del esquema `online_store`, restauración del `Dump.sql` y ajuste de credenciales en `database.yaml` |
| 2 | Error al registrar un usuario nuevo: la tabla `customer` no existía | La conexión con MySQL funcionaba, pero la base estaba vacía porque no se había cargado el archivo con las tablas | Importar el archivo `.sql` desde phpMyAdmin sobre la base de datos del proyecto |
| 3 | Riesgo de rechazo de conexión por credenciales | El usuario `root` de XAMPP no lleva contraseña por defecto | Dejar el archivo de configuración acorde al entorno local |

**Lección aprendida:** es importante mantener sincronizados tanto los respaldos de la base de datos como el código del repositorio, y documentar paso a paso la configuración para evitar errores humanos cuando otra persona necesite instalar el sistema en su computadora.

## 7. Evaluación técnica del sistema

El proyecto cumple con el objetivo académico de simular una plataforma de comercio electrónico funcional, y constituye una base adecuada para comprender el flujo completo de una aplicación web. No obstante, se identificaron áreas de mejora:

- **Frontend:** las vistas usan plantillas HTML con Jinja2 y Bootstrap. El diseño original era muy elemental y rígido, con poca modularidad de estilos y oportunidades de mejora en adaptabilidad a dispositivos móviles.
- **Backend:** la lógica y el enrutamiento se concentran en un solo archivo (`app.py`). Se recomienda refactorizar con Blueprints de Flask (autenticación, productos, carrito y panel administrativo).
- **Persistencia:** las consultas SQL están dentro de las funciones de ruta. Un ORM como SQLAlchemy reduciría el riesgo de inyección SQL y simplificaría el mantenimiento.
- **Validaciones y excepciones:** el control de errores y entradas del usuario es mínimo. Se requieren validaciones en cliente (JavaScript) y servidor, y manejo centralizado de excepciones.

## 8. Decisiones tomadas

1. Vender productos de la cafetería del Tec de Matehuala en línea, en lugar de una tienda genérica de abarrotes.
2. Enfocar la mejora a un público local (comunidad del Tecnológico Nacional de México campus Matehuala) y traducir la plataforma en su mayoría al español.
3. Limitar el alcance de la mejora solicitada a lo visual (frontend), mejorando el código HTML y CSS existente.
4. Adoptar el nombre "Transporte Express de Comida" (TEC) y un logotipo propio.
5. Usar GitHub como repositorio compartido, con todos los integrantes incluidos.

## 9. Preguntas abiertas

- **Productos:** ¿qué productos de la cafetería se publicarán y quién proporciona la lista con precios?
- **Pagos:** ¿se pagará en línea o al recoger el pedido?
- **Entrega:** ¿los pedidos se recogen en la cafetería o se entregan en el plantel?
- **Inventario:** ¿quién actualizará la disponibilidad de productos cuando se agote algo?
- **Identidad visual:** ¿quién define la paleta de colores y para qué fecha?
- **Base de datos:** confirmar con el equipo las tablas y permisos que no hayan quedado claros.

**Nota sobre el nombre:** el tester propuso como alternativas "TecBocados Matehuala", "CafeTec Express" y "Lonche Tec". El equipo adoptó finalmente "Transporte Express de Comida" (TEC); conviene confirmarlo formalmente con el resto del equipo.

## 10. Pendientes y plan de acción

| Pendiente | Responsable | Estado |
|---|---|---|
| Realizar el commit de los cambios de interfaz (logo, nombre y diseño) | Amaury | Realizado |
| Agregar el diagrama UML al repositorio y terminar el README | Amaury / Brauni | Realizado |
| Documentar la estrategia de ramas y cómo se integran los cambios | Amaury | Pendiente |
| Definir la paleta oficial de colores | Equipo | Realizado |
| Obtener la lista de productos y precios de la cafetería | Equipo | Pendiente |
| Traducir la interfaz al español | Leonardo / Brauni | En Proceso|
| Definir pasarelas de pago, inventario, promociones y notificaciones | Leonardo | Pendiente |
| Reforzar validación de usuarios y sesiones | Brauni | Realizado |
| Probar cada pantalla como Cliente y Administrador y registrar errores | Amaury | Realizado |
| Verificar que el proyecto se levante con un solo comando en cada computadora | Todos | En proceso |

## 11. Conclusiones

En estos primeros días el equipo logró levantar el proyecto en entorno local, restaurar la base de datos, crear la estructura base del repositorio con sus diagramas, definir el giro del negocio y renovar la identidad visual con un nuevo nombre, logotipo y una interfaz más moderna. Quedan por resolver la paleta de colores, el catálogo de productos, el flujo de pagos y entrega, la validación de usuarios y la documentación del repositorio. La división de tareas acordada el 5 de octubre y el seguimiento en esta bitácora permitirán avanzar de forma ordenada hacia el siguiente checkpoint.
