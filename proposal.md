# Propuesta TP DSW

## Grupo
### Integrantes
* (51219) Santiago, Lucas
* (50972) Hidalgo, Tomas
* (50408) Galarza, Nicolas
* (50729) Abuin, Leonel

### Repositorios
* [frontend app](http://hyperlinkToGihubOrGitlab)
* [backend app](http://hyperlinkToGihubOrGitlab)
*Nota*: si utiliza un monorepo indicar un solo link con fullstack app.

## Tema
### Descripción
*2 a 6 líneas describiendo el negocio (menos es más)*

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
|CRUD simple|1. CRUD Tipo producto<br>2. CRUD Pedido<br>3. CRUD Precio|
|CRUD dependiente|1. CRUD Producto {depende de} CRUD Tipo Producto<br>2. CRUD Precio {depende de} CRUD Producto|
|Listado<br>+<br>detalle| 1. Listado de productos filtrado por tipo de productos/marca, muestra nombre,descripcion,talle y precio => detalle CRUD Producto<br> 2. Listado de pedidos entregados filtrado por rango de fecha, muestra idPedido, fechaPedido nombre y apellido de cliente y total|
|CUU/Epic|1. Realizar un pedido<br>2. Reponer stock<br>3. Cancelar pedido<br>4. Envio de recordatorio de pedido por mail|


Adicionales para Aprobación
|Req|Detalle|
|:-|:-|
|CRUD |1. CRUD Tipo Habitacion<br>2. CRUD Servicio<br>3. CRUD Localidad<br>4. CRUD Provincia<br>5. CRUD Habitación<br>6. CRUD Empleado<br>7. CRUD Cliente|
|CUU/Epic|1. Reservar una habitación para la estadía<br>2. Realizar el check-in de una reserva<br>3. Realizar el check-out y facturación de estadía y servicios|


### Alcance Adicional Voluntario

*Nota*: El Alcance Adicional Voluntario es opcional, pero ayuda a que la funcionalidad del sistema esté completa y será considerado en la nota en función de su complejidad y esfuerzo.

|Req|Detalle|
|:-|:-|
|Listados |1. Estadía del día filtrado por fecha muestra, cliente, habitaciones y estado <br>2. Reservas filtradas por cliente muestra datos del cliente y de cada reserve fechas, estado cantidad de habitaciones y huespedes|
|CUU/Epic|1. Consumir servicios<br>2. Cancelación de reserva|
|Otros|1. Envío de recordatorio de reserva por email|

