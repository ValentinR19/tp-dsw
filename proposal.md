# Propuesta TP DSW

## Grupo
### Integrantes
* 51462 Joaquín García Forestello
* 50328 Guillermo Petri
* 47394 Ignacio Rodríguez Giménez
* 47395 Valentín Rodríguez Giménez
  
### Repositorios
* [frontend app](https://github.com/ValentinR19/tp-dsw-frontend)
* [backend app](https://github.com/ValentinR19/tp-dsw-backend)

## Tema
### Descripción
Sistema CRM para la gestión de clientes, productos y pedidos, orientado a la optimización de ventas y control de inventarios. Permite gestionar usuarios, productos, realizar pedidos y consultar el historial de ventas. Con enfoque en una experiencia de usuario sencilla y un control eficiente del inventario.

### Modelo
[Imagen](https://drive.google.com/file/d/1hRvQYCLcNNTwNJydMkqERwDMfqHMlLvO/view?usp=sharing)

### Alcance Funcional

| **Req**             | **Detalle**                                                                                                                |
|---------------------|----------------------------------------------------------------------------------------------------------------------------|
| **CRUD simple**      | 1. **CRUD de Clientes**: manejo de datos de clientes (nombre, email, teléfono, etc.). <br> 2. **CRUD de Productos**: gestión de productos (nombre, precio, stock, etc.). <br> 3. **CRUD de Usuarios**: creación, autenticación y gestión de roles (Admin, Vendedor, Cliente). <br> 4. **CRUD de Pedidos**: registro de pedidos realizados por los clientes, incluyendo productos seleccionados. |
| **CRUD dependiente** | 1. **CRUD de Líneas de Pedido**: dependiente de **Pedidos**, donde se registra cada producto seleccionado en un pedido. <br> 2. **Pedidos** depende de **Clientes** y **Productos** para ser creado. |
| **Listado + detalle**| 1. **Listado de Clientes**: filtro por nombre o email, muestra un listado de clientes. <br> 2. **Listado de Productos**: filtro por nombre o precio, muestra productos disponibles. <br> 3. **Listado de Pedidos**: filtro por fecha y estado, muestra los pedidos realizados. <br> Al seleccionar un pedido, muestra el detalle de ese pedido y las líneas de pedido asociadas. |


---


### Epics Propuestos 

| **Epic**                          | **Detalle**                                                                                                                  |
|------------------------------------|------------------------------------------------------------------------------------------------------------------------------|
| **Epic 1: Gestión de Clientes y Pedidos** | Este epic permite la creación de clientes y la gestión de pedidos asociados a esos clientes. <br> **Flujo**: Un administrador o vendedor crea un Cliente. El vendedor crea un Pedido para un cliente específico, seleccionando productos disponibles. Al guardar el pedido, se crean las Líneas de Pedido, donde cada producto elegido es registrado. <br> **Relación con otros epics**: **Clientes** sirve como entrada para **Pedidos**. Los **Pedidos** requieren **Productos** para ser completados. |
| **Epic 2: Gestión de Productos y Stock**  | Este epic se enfoca en la gestión de productos y stock. A medida que los productos son vendidos a través de los pedidos, el stock debe ser actualizado en tiempo real. <br> **Flujo**: Un administrador gestiona el catálogo de **Productos**: agregar, editar o eliminar productos. Cuando se genera un **Pedido**, el stock de los productos involucrados se debe descontar. <br> **Relación con otros epics**: **Productos** afecta a **Pedidos**. Cuando se realiza un pedido, el stock de los productos debe ser descontado automáticamente. |
| **Epic 3: Autenticación y Gestión de Usuarios** | Este epic se refiere a la gestión de acceso de los usuarios. <br> **Flujo**: El administrador puede registrar nuevos **Usuarios**. Los usuarios tienen un **Rol** (Admin, Vendedor, Cliente), y dependiendo de su rol, tienen acceso a distintas funcionalidades. La **Autenticación** debe permitir a los usuarios iniciar sesión y acceder a sus datos según el rol asignado. <br> **Relación con otros epics**: Los **Usuarios** registrados en **Autenticación** son necesarios para realizar acciones en los **Pedidos** o **Clientes**. |

---
