# Ecommer-GroceryStore-Cybercraftteam-
Equipo encargado de analizar y comprender el repositorio ya existente de un comercio electronico de una tienda de conveniencia.Donde se documentara el proceso que tuvo cada participante del proyecto y sus respectivas aportaciones y mejoras del proyecto mismo.
# El equipo
Nombres y roles asignados:
Rodriguez Flores Leonardo , Lider de requisitos y especificaciones
Rosas Vazquez Juan Diego , Arquitecto UML
Soto Cordova Brauni Alexander , Desarrollador de software
Tristan Cordova Amauri Ali, Analista de Calidad(QA) y pruebas
Fernandez Mendoza Diego, Especialista Ciberseguridad/Requisitos no funcionales

# GroStop E-Commerce - Guía de Instalación "A Prueba de Errores"

¡Hola! Si estás leyendo esto y no tienes mucha experiencia programando, no te preocupes. Esta guía te llevará **pasito a pasito** y de la manera más sencilla posible para que puedas instalar, configurar y hacer funcionar la tienda en línea **GroStop** en tu computadora, sin morir en el intento.

---

##  ¿Qué necesitamos antes de empezar? (Lo que debes tener instalado)
Para que este programa (hecho en Python y con bases de datos) funcione, tu computadora necesita tener tres cosas instaladas previamente:
1. **Python**: El lenguaje con el que está hecho el sitio web (si no lo tienes, descárgalo e instálalo desde su página oficial).
2. **XAMPP**: Un programa gratuito que sirve para crear una base de datos en tu propia computadora.
3. **Visual Studio Code (VS Code)**: El programa donde puedes ver y editar los archivos del proyecto.

---

##  Paso 1: Descargar el proyecto a tu computadora
1. Entra al repositorio de GitHub del proyecto.
2. Busca un botón verde que dice **"<> Code"** y dale clic.
3. Selecciona la opción que dice **"Download ZIP"**.
4. Una vez descargado el archivo comprimido, descomprímelo (ábrelo y extrae su contenido) en una carpeta fácil de encontrar, por ejemplo, en tu **Escritorio** o en tu carpeta de **Descargas**.

---

##  Paso 2: Encender el servidor de la base de datos (XAMPP)
Como nuestra tienda guarda información (como productos, carritos y usuarios), necesitamos encender el motor de base de datos:
1. Abre el programa **XAMPP Control Panel** en tu computadora.
2. Verás una lista de servicios. Busca los dos primeros: **Apache** y **MySQL**.
3. Dale clic al botón **"Start"** de **Apache**.
4. Dale clic al botón **"Start"** de **MySQL**. 
   *(Los botones deben ponerse de color verde. Si pasa eso, ¡vas muy bien!)*

---

##  Paso 3: Crear la base de datos en phpMyAdmin
Ahora vamos a crear el espacio físico donde se guardarán los datos de la tienda:
1. Abre tu navegador de internet favorito (Chrome, Edge, etc.).
2. Escribe esta dirección exacta en la barra de arriba y presiona Enter: 
   `http://localhost/phpmyadmin/`
3. Se abrirá una página web con muchas opciones. En la columna del lado izquierdo, busca y dale clic a un botón o enlace que dice **"Nueva"** (para crear una base de datos).
4. Te pedirá el nombre de la base de datos. Escribe exactamente esto (respeta las minúsculas y el guion bajo):
   `online_store`
5. Del lado derecho, busca el botón que dice **"Crear"** y dale clic.

---

##  Paso 4: Importar las tablas (Para que no te dé error)
La base de datos está vacía, así que necesitamos meterle las "tablas" que la página web va a usar para funcionar:
1. En la misma página de phpMyAdmin, haz clic sobre el nombre **`online_store`** que acabas de crear (lo verás en la columna de la izquierda).
2. En el menú de pestañas de arriba, busca una que dice **"Importar"** y dale clic.
3. Verás un botón que dice **"Seleccionar archivo"** (*Choose File*). Dale clic y busca en la carpeta de tu proyecto el archivo con terminación `.sql` que contiene la base de datos.
4. Baja hasta el final de la página y dale clic al botón verde que dice **"Continuar"**. 
   *(Te debe salir un mensaje verde diciendo que la importación se ha ejecutado con éxito).*

---

##  Paso 5: Configurar el archivo de conexión (`database.yaml`)
Tenemos que decirle a la página web cómo conectarse a tu base de datos de XAMPP:
1. Abre tu programa **Visual Studio Code**.
2. Arrastra la carpeta del proyecto de la tienda dentro de VS Code para abrirla.
3. En la lista de archivos de la izquierda, busca uno llamado **`database.yaml`**.
4. Ábrelo y revisa que su contenido sea exactamente así:
   ```yaml
   mysql_host : 'localhost'
   mysql_user: 'root'
   mysql_password : ''
   mysql_db : 'online_store'
   ```
   > ⚠️ **¡Ojo aquí!** Como XAMPP por lo general **no** usa contraseña para el usuario `root`, el espacio de `mysql_password` debe quedarse **vacío** entre las comillas simples (`''`). Si le pones algo por error, la página te rechazará el acceso.
5. Guarda los cambios presionando las teclas `Ctrl + S` (o `Cmd + S` en Mac).

---

##  Paso 6: Instalar las herramientas de Python (Librerías)
La aplicación web necesita ciertas extensiones de Python para funcionar:
1. Dentro de Visual Studio Code, abre la terminal integrada (puedes presionar las teclas `Ctrl + Shift + ´` o buscar en el menú superior *Terminal > New Terminal*).
2. Asegúrate de estar posicionado en la carpeta del proyecto y escribe el siguiente comando tal cual:
   ```bash
   pip install -r requirements.txt
   ```
3. Presiona **Enter** y espera a que la computadora descargue e instale todo solita. Cuando termine de correr letras, estará listo.

---

##  Paso 7: encender la página web
Ya casi acabamos, este es el último paso:
1. En esa misma ventana negra de la terminal, escribe el comando para arrancar el servidor:
   ```bash
   python run.py
   ```
2. Presiona **Enter**. Verás que la terminal te arroja un enlace en color azul o texto que dice algo como `Running on http://127.0.0.1:5000/`.
3. Abre tu navegador de internet, escribe o dale clic a ese enlace:
    **`http://127.0.0.1:5000/`**

¡Listo! Ya debería aparecer la página principal de la tienda en tu pantalla. Puedes registrar un usuario, probar los productos y navegar por el sitio sin problemas.

---

##  ¿Te salió algún error? (Soluciones rápidas)

* **Error: `Access denied for user 'root'@'localhost'`**
  * *¿Qué significa?* La contraseña de la base de datos está mal. 
  * *¿Cómo se arregla?* Ve al archivo `database.yaml` (Paso 5) y asegúrate de que el renglón de la contraseña esté completamente vacío: `mysql_password : ''`. Guarda el archivo y reinicia el programa.

* **Error: `MySQLdb.ProgrammingError: (1146, "La tabla ... no existe")`**
  * *¿Qué significa?* La base de datos está creada pero olvidaste hacer el Paso 4.


  * *¿Cómo se arregla?* Ve a phpMyAdmin, selecciona tu base de datos `online_store`, dale a la pestaña **Importar** y sube el archivo `.sql` de las tablas del proyecto.



