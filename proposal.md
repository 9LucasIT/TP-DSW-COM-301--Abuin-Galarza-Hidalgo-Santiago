# Propuesta TP DSW - Sportify

## Grupo: Sportify Team
### Integrantes
* (51219) Santiago, Lucas
* (50972) Hidalgo, Tomas
* (50408) Galarza, Nicolas
* (50729) Abuin, Leonel

### Repositorios
* **Frontend App:** [https://github.com/leoabuin/proyecto-venta-productos-front-end.git](https://github.com/leoabuin/proyecto-venta-productos-front-end.git)
* **Backend App:** [https://github.com/leoabuin/proyecto-venta-productos](https://github.com/leoabuin/proyecto-venta-productos)

## Tema
### Descripción
**Sportify** es una plataforma de e-commerce especializada en indumentaria y artículos deportivos. El sistema permite a los usuarios finales registrarse, gestionar su perfil y realizar pedidos mediante un flujo de carrito de compras. Los clientes pueden monitorear sus pedidos y cancelarlos de forma autónoma siempre que permanezcan en estado **"Pendiente"**.

Para la gestión interna, el sistema cuenta con un **Panel de Administración (Dashboard)** donde el personal (rol Empleado) puede administrar el catálogo completo: Marcas, Categorías, Géneros, Distribuidores y Productos. 

**Reglas de Negocio Destacadas:**
1. **Baja Lógica:** Los productos no se eliminan físicamente de la base de datos para preservar la integridad histórica de las órdenes de compra; en su lugar, se implementa una baja lógica (`isContinuated: false`).
2. **Gestión de Precios:** Los empleados pueden programar y actualizar los precios de los productos, manteniendo un historial de cambios.
3. **Seguridad Robusta:** Autenticación mediante **JWT** almacenado en **Cookies HttpOnly** para prevenir ataques XSS, con autorización diferenciada por roles mediante Middlewares.

### Modelo de Dominio
El diagrama representa las entidades principales (Producto, Marca, Categoría, Orden, Ítem de Orden, Usuario, Distribuidor, Género y Comentario) y sus relaciones.

* **Imagen del Modelo:** [Visualizar Modelo de Dominio](docs/images/Modelo de dominio TP DSW Sportify.png)

---

## Alcance Funcional 

### Alcance Mínimo (Regularidad)

| Req | Detalle |
| :--- | :--- |
| **CRUD Simple** | 1. CRUD Categoría<br>2. CRUD Marca<br>3. CRUD Género<br>4. CRUD Usuario |
| **CRUD Dependiente** | 1. **CRUD Producto**: Relacionado con Categoría, Marca y Género.<br>2. **CRUD Precio**: Historial dependiente de Producto.<br>3. **CRUD Distribuidor**: Gestión de proveedores vinculados al stock. |
| **Listado + Detalle** | 1. **Catálogo de Productos**: Filtrado dinámico por Categoría, Marca y Género. Incluye vista de detalle.<br>2. **Gestión de Pedidos**: Listado histórico de órdenes por usuario con estados (Pendiente / Cancelado). |
| **CUU / Epic** | 1. **Realizar Pedido**: Flujo completo de carrito y persistencia de orden.<br>2. **Cancelación de Pedido**: Lógica de anulación por parte del cliente.<br>3. **Notificación Automática**: Envío de comprobante de pedido vía Email (EmailJS/SMTP). |

### Alcance Adicional (Aprobación / Dashboard Admin)

| Req | Detalle |
| :--- | :--- |
| **Dashboard de Gestión** | Panel centralizado para el empleado que permite la administración total de las entidades del sistema sin salir de la interfaz administrativa. |
| **Seguridad Avanzada** | Implementación de **Role-Based Access Control (RBAC)** con Guards en el Frontend y Middlewares en el Backend para proteger rutas sensibles. |
| **Sistema de Feedback** | Implementación de **Comentarios y Calificaciones** donde los usuarios pueden interactuar con los productos adquiridos. |
| **Optimización de UI** | Implementación de Loading Spinners, validaciones de formularios con **Zod** (Backend) y **Reactive Forms** (Frontend). |

---

### Alcance Adicional Voluntario

| Req | Detalle |
| :--- | :--- |
| **Filtros de Ofertas** | Atributo `isOffer` en productos que permite destacar artículos en la página principal y filtrar en el catálogo. |
| **Lista de Favoritos** | Funcionalidad para que el cliente guarde productos de interés para compras futuras (Wishlist). |
| **Infraestructura Cloud** | Despliegue automatizado (CI/CD) en **Railway** utilizando Docker/Nginx para el Frontend y Node.js para el Backend. |

