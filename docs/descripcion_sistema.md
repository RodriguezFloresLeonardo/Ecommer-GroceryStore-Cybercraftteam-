# Descripción del Sistema: E-commerce Grocery Store

**Repositorio:** [RodriguezFloresLeonardo/Ecommer-GroceryStore-Cybercraftteam-](https://github.com/RodriguezFloresLeonardo/Ecommer-GroceryStore-Cybercraftteam-/tree/main)



## 1. Visión General
**Grocery Store** es una plataforma web de comercio electrónico diseñada para la venta y gestión de productos de abarrote y supermercado en línea. El sistema permite a los clientes explorar un catálogo digital, gestionar su carrito y realizar compras, mientras ofrece a los administradores herramientas para el control del inventario y el seguimiento de pedidos.



## 2. Arquitectura y Tecnologías

* **Frontend:**
  * **HTML5 / CSS3:** Estructuración y diseño responsivo de la interfaz de usuario.
  * **JavaScript (Vanilla JS):** Dinamismo en la navegación, manipulación del DOM y consumo de servicios REST.
* **Backend:**
  * **Java (Spring Boot):** Framework principal para la lógica de negocio, arquitectura en capas (MVC) y exposición de servicios API REST.
* **Base de Datos:**
  * **MySQL:** Sistema de gestión de bases de datos relacionales para el almacenamiento de usuarios, productos, categorías, carrito y órdenes.

---

## 3. Funcionalidades Principales

### 1. Módulo de Usuarios y Autenticación
* Registro de usuarios y gestión de perfiles.
* Sistema de autenticación e inicio de sesión.
* Control de acceso basado en roles (*Cliente* y *Administrador*).

### 2. Módulo de Catálogo y Navegación
* Visualización interactiva de productos por categorías (frutas, verduras, lácteos, abarrotes, etc.).
* Búsqueda dinámica y filtrado de artículos.
* Vista detallada con información del producto (precio, stock, descripción e imagen).

### 3. Módulo de Carrito y Compras
* Adición, modificación y eliminación de productos en el carrito en tiempo real.
* Cálculo automático de subtotales, impuestos y costos finales.
* Módulo de checkout para procesar y confirmar la orden de compra.

### 4. Panel de Administración (Backoffice)
* **Gestión de Inventario (CRUD):** Alta, baja, modificación y consulta de productos.
* **Gestión de Categorías:** Organización de los productos dentro del catálogo.
* **Gestión de Pedidos:** Visualización y seguimiento del estado de las compras realizadas por los clientes.
