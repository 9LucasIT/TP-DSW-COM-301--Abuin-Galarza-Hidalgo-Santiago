# TP DSW — Sportify: Gestión de Productos Deportivos

Repositorio central del Trabajo Práctico de Desarrollo de Software.

**Sportify** es una aplicación web full stack diseñada para la administración y venta de artículos deportivos. Permite la gestión completa de productos, categorías, marcas, distribuidores y usuarios, con un sistema de permisos basado en roles.

![Sportify-Banner](docs/images/banner.png) ## Estructura del Proyecto

El proyecto está dividido en dos grandes bloques:

- `frontend/`: Aplicación cliente desarrollada con **Angular 18+**.
- `backend/`: API REST desarrollada con **Node.js, Express y Mikro-ORM**.

## Repositorios

- **Frontend:** [https://github.com/leoabuin/proyecto-venta-productos-front-end](https://github.com/leoabuin/proyecto-venta-productos-front-end)
- **Backend:** [https://github.com/leoabuin/proyecto-venta-productos](https://github.com/leoabuin/proyecto-venta-productos)

## Aplicación en Producción

🚀 **Sitio web:** [https://proyecto-venta-productos-front-end-production.up.railway.app/](https://proyecto-venta-productos-front-end-production.up.railway.app/)

---

## Stack Tecnológico

### Backend
- **Entorno:** Node.js + Express + TypeScript
- **Persistencia:** Mikro-ORM + MySQL
- **Seguridad:** - Autenticación mediante **JWT (JSON Web Tokens)**.
  - Almacenamiento seguro en **Cookies HttpOnly**.
  - Encriptación de contraseñas con **Bcrypt**.
  - Middlewares de autorización por **Roles** (Cliente / Empleado).

### Frontend
- **Framework:** Angular 18 + TypeScript
- **Comunicación:** HttpClient con **Interceptors** para manejo de credenciales.
- **Estilos:** Bootstrap / CSS personalizado.

---

## 🔐 Seguridad y Autorización

Un punto clave de este proyecto es la protección de las rutas del servidor. Se implementaron middlewares para asegurar que solo los usuarios autorizados realicen cambios:

* **Público:** Visualización de productos, marcas y categorías.
* **Privado (Empleado):** CRUD de productos, gestión de distribuidores, marcas y géneros.

> **Middleware de validación:** El servidor verifica la presencia y validez del token en cada petición sensible, asegurando que el `rol` del usuario coincida con la acción solicitada.

---

## Puesta en marcha rápida

### 1) Instalar dependencias

```bash
# En la carpeta del Backend
pnpm install

# En la carpeta del Frontend
npm install
