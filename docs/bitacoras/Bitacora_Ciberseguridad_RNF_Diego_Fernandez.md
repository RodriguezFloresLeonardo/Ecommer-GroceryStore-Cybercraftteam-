# Bitácora de Operaciones, Despliegue y Gestión de Incidentes
Proyecto: GroStop (Plataforma E-Commerce / Flask)
Rol Operativo: Especialista en Ciberseguridad / Ingeniero de Sistemas
## 1. Resumen Ejecutivo y Alcance Técnico
En este proyecto nos encargamos de echar a andar en la computadora la tienda en
línea GroStop, la cual utiliza Python con Flask para la parte de la página y una base de
datos en MySQL mediante XAMPP. Durante el proceso revisamos que todo quedara
bien configurado, desde la conexión con el servidor hasta la estructura de las tablas,
asegurándonos de que la aplicación funcionara de manera correcta y segura.
## 2. Bitácora Cronológica de Actividades y Conceptos Abordados
Para empezar, lo primero que hicimos fue encender los servicios de Apache y MySQL
en el panel de control de XAMPP para que la base de datos y el servidor web
respondieran localmente. Después revisamos cómo estaba armada la base de datos
llamada online_store para asegurarnos de que coincidiera con lo que la página web iba
a necesitar. También abrimos el archivo de configuración llamado database.yaml para
revisar los datos de acceso, comprobando que el usuario fuera el correcto y que la
contraseña estuviera configurada tal como lo pedía el entorno local. Por último,
instalamos las librerías necesarias de Python ejecutando el comando correspondiente
en la terminal para que no faltara ningún componente al momento de conectar el código
con la base de datos.
## 3. Registro de Incidencias, Dificultades y Análisis de Fallos
Durante las pruebas nos topamos con un problema cuando intentamos registrar un
usuario nuevo, ya que la página nos arrojó un error que decía que la tabla llamada
customer no existía en la base de datos. Investigando el fallo, nos dimos cuenta de que
aunque la conexión con MySQL sí funcionaba, la base de datos estaba vacía porque
faltaba cargar el archivo con las tablas del proyecto. Para solucionarlo, entramos a
phpMyAdmin en el navegador, seleccionamos nuestra base de datos y usamos la
opción de importar para subir el archivo de respaldo con extensión punto sql, lo que
dejó listas todas las tablas que hacían falta. Además, revisando la parte de seguridad y
accesos, tuvimos en cuenta que en XAMPP el usuario por defecto es root y no lleva
contraseña, por lo que dejamos el archivo de configuración tal cual para evitar que el
sistema rechazara la conexión.
4. Conclusiones y Criterios de Aseguramiento
Al final, logramos que el sitio web levantara sin problemas en la dirección local del
navegador. Con esta experiencia comprobamos lo importante que es tener
sincronizados tanto los respaldos de la base de datos como el código del repositorio.
Visto desde el lado de la ciberseguridad y la operación, tener este tipo de notas y guías
paso a paso nos ayuda muchísimo a evitar errores humanos cuando alguien más
necesita configurar el sistema en su propia computadora.
