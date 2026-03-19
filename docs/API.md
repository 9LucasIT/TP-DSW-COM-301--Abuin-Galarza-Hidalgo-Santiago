```markdown
# Documentación de API - Sportify

Esta API utiliza una arquitectura RESTful y responde en formato JSON.

### Base URL
`http://localhost:3000/api`

---

## Autenticación

La seguridad se maneja mediante **JWT**. El servidor busca el token en:
1.  **Cookie `token`** (Enviada automáticamente por el navegador).
2.  **Header `Authorization: Bearer <token>`** (Para pruebas en Postman).

---

## Endpoints Principales

### 📦 Productos (`/api/products`)
| Método | Endpoint | Descripción | Requisito |
| :--- | :--- | :--- | :--- |
| GET | `/` | Listar todos los productos | Público |
| GET | `/:id` | Ver detalle de producto | Público |
| POST | `/` | Crear producto | **Empleado** |
| PUT | `/:id` | Editar producto completo | **Empleado** |
| PATCH | `/:id` | Editar campos específicos | **Empleado** |
| DELETE | `/:id` | Eliminar producto | **Empleado** |

### 🚚 Distribuidores (`/api/distributors`)
| Método | Endpoint | Descripción | Requisito |
| :--- | :--- | :--- | :--- |
| GET | `/` | Listar todos | **Empleado** |
| POST | `/` | Registrar distribuidor | **Empleado** |
| DELETE | `/:id` | Dar de baja | **Empleado** |

### 👤 Usuarios y Sesión (`/api/users`)
| Método | Endpoint | Descripción | Requisito |
| :--- | :--- | :--- | :--- |
| POST | `/login` | Iniciar sesión (Genera Cookie) | Público |
| POST | `/register` | Registrar nuevo cliente | Público |
| POST | `/logout` | Cerrar sesión (Limpia Cookie) | Público |


### Ordenes (`/api/orders`)
| Método | Endpoint | Descripción | Requisito |
| :--- | :--- | :--- | :--- |
| POST | `/placeOrder` | Realizar Pedido (genera pedido) | **Cliente** |
| POST | `/cancelOrder` | Cancelar Pedido | **Cliente** |
| GET | `/findOrderbyUser` | Ver detalle del Pedido | **Cliente** |
| GET | `/getAllOrders` | Obtener ordenes para dashboard | **Empleado** |

---

## Códigos de Error

- `401 Unauthorized`: Token no encontrado o expirado.
- `403 Forbidden`: El usuario está autenticado pero no tiene el rol **Empleado**.
- `404 Not Found`: El recurso solicitado no existe.
- `400 Bad Request`: Error en la validación de datos (Sanitize).

---

## Middlewares de Validación
Cada petición de escritura (POST/PUT/PATCH) pasa por un middleware de **Sanitización** que filtra campos prohibidos y asegura la integridad de los datos antes de persistirlos en MySQL.