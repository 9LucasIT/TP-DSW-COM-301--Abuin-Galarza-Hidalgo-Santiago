# Propuesta TP DSW

## Grupo
### Integrantes
* (51219) Santiago, Lucas
* (50972) Hidalgo, Tomas
* (50408) Galarza, Nicolas
* (50729) Abuin, Leonel

### Repositorios
* [frontend app](https://github.com/leoabuin/proyecto-venta-productos-front-end.git)
* [backend app](https://github.com/leoabuin/proyecto-venta-productos)


## Tema
### Descripción
*Nuestra aplicacion es un ecommerce en donde se vende articulos de indumentaria deportiva. En este se crea una cuenta, se inicia sesion y ya puede realizar un pedido. El cliente va agregando productos a su carrito y una vez lo decida, va al apartado de carrito donde se van a encontrar todos los productos que agrego y finaliza el pedido. El cliente si se arrepiente puede cancelar el pedido siempre y cuando el pedido se encuentre en estado 'Pendiente'. De parte del empleado, tambien se crea una cuenta y puede agregar, modificar y eliminar las marcas, categorias, distribuidores y productos. (como regla de negocio decidimos que el producto no se elimina para evitar conflictos con los clientes que compraron ese producto. Se puede dar de baja logica). Tambien el empleado puede programar un cambio de precio del producto en el apartado 'agregar precio'*

### Modelo
![imagen del modelo]()

*Nota*: incluir un link con la imagen de un modelo, puede ser modelo de dominio, diagrama de clases, DER. Si lo prefieren pueden utilizar diagramas con [Mermaid](https://mermaid.js.org) en lugar de imágenes.
Modelo de dominio: [https://drive.google.com/drive/folders/1plfqKYozPPYJY6YgyQEiOHqnKOYbRe8-]
## Alcance Funcional 

### Alcance Mínimo

*Nota*: el siguiente es un ejemplo para un grupo de 3 integrantes para un sistema de hotel. El 

Regularidad:
|Req|Detalle|
|:-|:-|
|CRUD simple|1. CRUD Category<br>2. CRUD Brand<br>3. CRUD Price <br>4. CRUD User|
|CRUD dependiente|1. CRUD Product {depende de} CRUD Category y Brand<br>2. CRUD Price {depende de} CRUD Product <br>3. CRUD Order {depende de} Product y User|
|Listado<br>+<br>detalle| 1.  Listado de productos filtrado por categoria, muestra nombre,descripcion,talle y precio => detalle CRUD Producto<br> 2. Listado de pedidos de un usaurio(los pedidos pueden estar en estado 'pendientes', que se pueden cancelar y en estado 'cancelado')|
|CUU/Epic|1. Realizar un pedido<br>2. Reponer stock<br>3. Cancelar pedido<br>4. Envio de recordatorio de pedido por mail|


Adicionales para Aprobación
|Req|Detalle|
|:-|:-|
|CRUD |1. CRUD Tipo Producto<br>2. CRUD Precio<br>3. CRUD Cliente<br>4. CRUD Pedido<br>5. CRUD Producto<br>6. CRUD Marca<br>7. CRUD -|
|CUU/Epic|1. Realizar un pedido<br>2. Reponer stock<br>3. Cancelar un pedido<br>4. Envio de recordatorio de pedido por mail|


### Alcance Adicional Voluntario

*Nota*: El Alcance Adicional Voluntario es opcional, pero ayuda a que la funcionalidad del sistema esté completa y será considerado en la nota en función de su complejidad y esfuerzo.

|Req|Detalle|
|:-|:-|
|Listados |1. Listado de productos filtrado por categoria, muestra nombre,descripcion,talle y precio <br>2. Listado de pedidos de un usaurio(los pedidos pueden estar en estado 'pendientes', que se pueden cancelar y en estado 'cancelado')|
|CUU/Epic|1. 3. Cancelar un pedido<br>2. Reponer stock|
|Otros|1. Envio de recordatorio de pedido por mail|

