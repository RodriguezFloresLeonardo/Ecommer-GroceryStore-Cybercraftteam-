# Informe de Arquitectura de Software - Sistema GroStop

## I. Ficha de participación y propósito del rol

Durante el desarrollo del sistema **GroStop** (`ECommerce-Grocery-Store`) participé como **Arquitecto de Software / Modelado UML**.

Mi responsabilidad principal fue comprender la estructura del sistema, revisar cómo se relacionan sus componentes y representar su funcionamiento mediante diagramas UML. Para realizar el modelado fue necesario instalar y ejecutar el proyecto localmente, revisar su código, navegar las funciones disponibles y analizar la estructura de la base de datos.



## II. Resumen de actividades realizadas desde mi rol

* **Instalación y preparación del proyecto:** Participé en la puesta en marcha del repositorio en Windows, configurando Python, el entorno virtual y las dependencias necesarias para poder ejecutar la aplicación.
* **Configuración de la base de datos:** Instalé y configuré MySQL, creé la base de datos `grocery_store` e importé el archivo `Dump.sql` para disponer de la estructura y datos requeridos por el sistema.
* **Revisión funcional:** Navegué la aplicación para identificar los tipos de usuario y las operaciones visibles. Se comprobaron los accesos como cliente, administrador y vendedor, además de funciones relacionadas con productos, pedidos, carrito y ofertas.
* **Análisis de la estructura de datos:** Revisé las entidades, atributos, claves primarias y claves foráneas definidas en `Dump.sql`. Se identificaron 15 tablas y una vista denominada `rating_table`.
* **Modelado UML:** Con la información obtenida del código, la navegación y la base de datos elaboré un diagrama de casos de uso y un diagrama de clases/entidades del sistema.
* **Integración visual:** También se incorporaron archivos modificados de `templates` y `static` para actualizar imágenes, estilos y apariencia de la interfaz, verificando posteriormente que la aplicación continuara funcionando.



## III. Problemas técnicos enfrentados y soluciones aplicadas

* **Problema 1 - Python no reconocido al crear el entorno virtual:** Al intentar ejecutar `python -m venv venv`, Windows indicó que Python no se encontraba. Se corrigió la instalación/configuración de Python y posteriormente se pudo crear y utilizar el entorno virtual.
* **Problema 2 - Entorno virtual con rutas incorrectas:** Al instalar `requirements.txt` apareció un error porque `pip` intentaba utilizar una ruta perteneciente a otra computadora. Se recreó/configuró correctamente el entorno virtual y se instalaron nuevamente las dependencias.
* **Problema 3 - Git no reconocido:** Al intentar clonar el repositorio desde CMD, el comando `git` no estaba disponible. Fue necesario instalar Git para Windows y comprobar su disponibilidad antes de continuar.
* **Problema 4 - Configuración inicial de MySQL:** Por ser la primera vez que utilizaba MySQL fue necesario instalar el servidor, crear `grocery_store` e importar `Dump.sql`. La importación se verificó con `SHOW TABLES`, obteniendo las entidades del proyecto.
* **Problema 5 - Error 1045 de MySQL al registrarse:** Aunque la página web cargaba, al intentar registrar un usuario Flask mostraba `Access denied for user 'root'@'localhost'`. Se determinó que la contraseña configurada en `database.yaml` no coincidía con la contraseña válida del usuario root.
* **Problema 6 - Recuperación de acceso a MySQL:** Se inició MySQL temporalmente con una configuración especial utilizando el archivo `my.ini` y memoria compartida, se restableció la contraseña de root y se actualizó `database.yaml`. Después de reiniciar el servidor y Flask, el registro de clientes y administradores funcionó correctamente.
* **Problema 7 - Nombre de la base de datos:** El archivo `database.yaml` originalmente utilizaba `online_store`, mientras que durante la instalación se creó `grocery_store`. Se actualizó la configuración para que la aplicación apuntara a la base utilizada localmente.



## IV. Análisis y modelado UML realizado

Una vez que el sistema pudo ejecutarse correctamente, el modelado se realizó a partir de dos fuentes principales: el comportamiento observable al navegar la aplicación y las relaciones presentes en la base de datos. Esto permitió evitar representar funciones que no estuvieran sustentadas por el proyecto.

* **Diagrama de casos de uso:** Se identificaron como actores principales Cliente, Administrador y Vendedor. El diagrama representa las operaciones comprobadas para cada tipo de usuario y permite visualizar de manera general cómo interactúan con el sistema.
* **Diagrama de clases/entidades:** Se construyó a partir del esquema de MySQL. Se representaron entidades como `admin`, `customer`, `seller`, `product`, `category`, `cart`, `orders`, `offer` y `delivery_boy`, además de tablas asociativas como `sells`, `selects`, `associated_with`, `admin_views` y `rates_order_delivery`.
* **Relaciones de datos:** Se analizaron las claves foráneas para establecer las conexiones entre entidades. Por ejemplo, `product` se relaciona con `admin` y `category`; `orders` se relaciona con `cart` y `delivery_boy`; y `product_feedback` relaciona productos con clientes.
* **Vista de calificaciones:** Se distinguió `rating_table` como una vista y no como una tabla independiente. Esta vista calcula el promedio de las calificaciones de los productos a partir de `product_feedback`.



## V. Hallazgos y observaciones de arquitectura

* **Separación de responsabilidades:** El sistema utiliza Flask para la lógica web, `templates` para las vistas HTML, `static` para recursos visuales y MySQL para persistencia de información.
* **Modelo de datos amplio:** La base contiene relaciones para clientes, vendedores, administradores, repartidores, productos, pedidos, ofertas, reseñas y carritos, lo que permite representar distintas áreas de una tienda en línea.
* **Diferencia entre base de datos e interfaz:** Se detectaron elementos existentes en el esquema, como reseñas y calificaciones, que no necesariamente aparecen como funciones activas o claramente accesibles en todas las pantallas revisadas. Por ello se incluyeron en el modelo de entidades sin atribuir funciones no comprobadas a los actores.
* **Configuración sensible:** `database.yaml` contiene datos de conexión a MySQL, por lo que debe evitarse publicar contraseñas reales en repositorios compartidos.



## VI. Dudas iniciales y aprendizaje obtenido

Al inicio, una de las principales dificultades fue comprender cómo pasar de observar una aplicación funcionando a representar correctamente su arquitectura. También fue necesario aprender a interpretar errores de consola, configurar MySQL y entender la utilidad de las claves primarias y foráneas. Al revisar el código y la base de datos entendí que un diagrama UML no debe construirse únicamente a partir de lo que se ve en la interfaz, sino también de las relaciones y responsabilidades internas del sistema.

El proceso de instalación resultó útil para mi rol porque permitió conocer de forma práctica las dependencias entre Flask, Python y MySQL. Resolver los errores antes del modelado también permitió comprobar qué funciones estaban realmente disponibles y cuáles solamente estaban contempladas en el esquema de datos.



## VII. Conclusiones personales

Esta práctica me permitió comprender mejor el trabajo de un Arquitecto de Software. Mi participación no se limitó a dibujar diagramas: primero fue necesario instalar, ejecutar, probar y analizar el sistema. A partir de esa revisión pude transformar la información técnica del proyecto en modelos UML que facilitan entender sus actores, funcionalidades, entidades y relaciones.

También aprendí que documentar los problemas encontrados durante la instalación es importante, ya que estos pueden revelar dependencias y decisiones de configuración que forman parte de la arquitectura real del sistema. Finalmente, el diagrama de casos de uso y el diagrama de clases/entidades sirven como documentación para que otros integrantes del equipo puedan comprender el proyecto sin tener que revisar inmediatamente todo el código fuente.



## VIII. Evidencias generadas
* **Evidencia 1:** Proyecto `ECommerce-Grocery-Store` ejecutándose localmente mediante Flask.
* **Evidencia 2:** Base de datos `grocery_store` importada y funcionando en MySQL.
* **Evidencia 3:** Registro e inicio de sesión comprobados después de corregir la autenticación de MySQL.
* **Evidencia 4:** Diagrama UML de casos de uso.
* **Evidencia 5:** Diagrama UML de clases/entidades construido a partir de `Dump.sql`.
* **Evidencia 6:** Interfaz actualizada mediante los archivos de `templates` y `static`.

* **Evidencia 1:** Proyecto `ECommerce-Grocery-Store` ejecutándose localmente mediante Flask.
* **Evidencia 2:** Base de datos `grocery_store` importada y funcionando en MySQL.
* **Evidencia 3:** Registro e inicio de sesión comprobados después de corregir la autenticación de MySQL.
* **Evidencia 4:** Diagrama UML de casos de uso.
* **Evidencia 5:** Diagrama UML de clases/entidades construido a partir de `Dump.sql`.
* **Evidencia 6:** Interfaz actualizada mediante los archivos de `templates` y `static`.
