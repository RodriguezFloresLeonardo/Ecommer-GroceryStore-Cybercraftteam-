# BITÁCORA DEL LÍDER
Análisis de Integración y Evaluación de Cumplimiento de Requisitos
________________________________________
## 1. Ficha de Onboarding del Líder de Requisitos
●	Rol: Líder de Requisitos / Analista de Sistemas
●	Líder de Proyecto / Desarrollador: Leonardo Rodriguez Flores
●	Proyecto Evaluado: E-Commerce Grocery Store (Proyecto de Abarrotes)
________________________________________
## 2. Diagnóstico de Entrada y Propósito de la Evaluación
Como Líder de Requisitos recién incorporado al equipo, se realizó una revisión del código fuente y del repositorio para evaluar si la solución técnica actual responde a las necesidades reales del negocio y cumple con la especificación funcional requerida para una tienda de abarrotes en línea.
________________________________________
## 3. Matriz de Cumplimiento de Requisitos Funcionales (RF)
1.	1: Visualización y Filtro del Catálogo de Abarrotes
a.	Estado: Cumplido parcialmente.
b.	Hallazgo: El sistema presenta la estructura básica para desplegar productos por categoría. Se requiere verificar la paginación y la búsqueda en tiempo real.
2.	: Gestión del Carrito de Compras
a.	Estado: Cumplido.
b.	Hallazgo: Se identifican los mecanismos para agregar, modificar cantidades y eliminar ítems de la cesta antes de proceder al pago.
3.	: Módulo de Registro y Autenticación de Usuarios
a.	Estado: Incompleto
b.	Hallazgo: Es necesario validar las políticas de seguridad en el manejo de credenciales y la persistencia de sesiones ya que no se validan aun los correos utilizados.
4.	: Procesamiento de Pedidos y Finalización de Compra (Checkout)
a.	Estado: Sin finalizar.
b.	Hallazgo: El flujo de compra registra la orden, pero se requiere la especificación exacta de las pasarelas de pago a integrar.
________________________________________
## 4. Evaluación de Requisitos No Funcionales 
1.	: Usabilidad y Experiencia de Usuario (UX)
a.	Evaluación: Aceptable a medias. La navegación es directa para compras rápidas de productos de primera necesidad.
2.	: Trazabilidad y Gestión de Cambios (CASE)
a.	Evaluación: Excelente. La estructura de commits e historial en Git permite mapear requerimientos directamente con los cambios en el código.
3.	: Escalabilidad y Rendimiento
a.	Evaluación: Requiere Pruebas de Carga. Se recomienda evaluar la latencia en las respuestas de la base de datos ante picos de consulta.
________________________________________
## 5. Brechas Identificadas (Gap Analysis) y Necesidades del Negocio
●	Validación de Inventarios: Falta definir el requerimiento de control de stock en tiempo real para evitar compras de productos agotados.
●	Manejo de Promociones: No se encuentra especificado el módulo de cupones o descuentos por volumen.
●	Notificaciones de Pedido: Se detecta la necesidad de enviar confirmaciones por correo electrónico o mensajes de estado sobre el envío.
________________________________________
6. Plan de Acción del Líder de Requisitos
●	Mejora en el apartado visual(frontend): El enfoque que se le dará a la mejora solicitada será puramente una mejora visual para los consumidores finales del producto mejorando el ya existente codigo html y css.
●	Adecuar el producto para un publico conocido: Se le dara el enfoque a un publico local de la institucion Tecnm campus matehuala ademas de traducirlo en su mayoria al español para su mejor entendimiento.
