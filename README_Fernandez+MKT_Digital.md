## CREACION BASE DE UNA APP PARA OPTIMIZACION DE MARKETING DIGITAL


### Problema:

Hoy en día, existen múltiples plataformas a través de las cuales realizar marketing de manera online, plataformas como Google, Facebook, Mercado Libre, Twitter, Tiktok, entre otros. La cantidad de posibilidades es inmensa, cada uno de estos canales ofrece distintas funcionalidades y tienen sus propios usuarios.

Ante esto nos surge la pregunta de cómo distribuir dicho presupuesto. Al realizar esta pregunta a profesionales del marketing, la mayoría de ellos asegura que distribuyen su presupuesto de una manera intuitiva, basándose en el mercado que tienen y en qué canales les resultaban más cómodos.

Esto presenta un problema ya que existe un fenómeno que está dañando la eficiencia de las campañas de anuncios digitales que corren hoy en día. Este problema se conoce como saturación de canales y se da porque, a medida que la inversión en marketing aumenta, las ventas aumentan a un ritmo cada vez menor debido a que se saturan los canales, y como consecuencia, cae el retorno de los anuncios realizados por plataformas digitales.

### Descripción del Problema:

1. **Gestión de Clientes y Empleados**: Necesitamos una base de datos que nos permita registrar la información de los clientes que realizan el marketing digital, así como de los empleados involucrados en la alocaciòn del presupuesto o encargados de atención al cliente.

2. **Gestión de Tipos de Servicio**: Es importante poder clasificar los servicios según su tipo, ya sea una simplea alocaciòn de presupuesto multiplataforma, un servicio personalizado para un cliente grande. Esto nos ayudará a organizar mejor el flujo de trabajo y adaptar nuestros servicios según las necesidades del cliente.

3. **Gestión de Plataformas donde se alocará el presupuesto en Marketing Digital**: La base de datos debe permitirnos registrar la performance en las plataformas así como su estado (mostrar si la plataforma se encuentra o no saturada). Esto es fundamental para garantizar una asignación eficiente de recursos en las múltiples plataformas.

4. **Registro de Ventas**: Necesitamos un sistema que pueda registrar de manera detallada cada venta realizada, incluyendo la fecha y hora de la venta, el cliente que la realizó, el empleado que atendió la reserva y el tipo de servicio.

5.  **Registro de Cobro**: Necesitamos un sistema que pueda registrar de manera detallada cada cobro realizado, incluyendo la fecha y hora del mismo, el pago del cliente, el empleado que certificó el cobro y el tipo de servicio cobrado.

### Objetivo:

Diseñar e implementar una base de datos relacional que satisfaga todas las necesidades de gestión de la alocación del marketing digital para nuestro sistema de gestión  Esta base de datos deberá ser eficiente, escalable y fácil de mantener, permitiendo una gestión ágil y precisa de todas las operaciones relacionadas con las alocaciones pertinentes.


## Descripción de la Base de Datos - Gestión de Alocación de Marketing Digital

Esta base de datos está diseñada para gestionar la alocación del dinero para el marketing digital multiplataforma, así como la información relacionada con clientes, empleados, tipos de servicios, plataforma en donde se aloca, ventas y cobros. A continuación se detallan los elementos principales de la base de datos:

### Tablas:

1. **CLIENTE**:
   - Almacena información sobre los clientes que realizan reservas.
   - Atributos: IDCLIENTE, NOMBRE, TELEFONO, CORREO.

2. **EMPLEADO**:
   - Contiene información sobre los empleados involucrados en el proceso de reservas.
   - Atributos: IDEMPLEADO, NOMBRE, TELEFONO, CORREO, IDRESTAURANTE.

3. **DUEÑO**:
   - Guarda datos sobre los dueños de los restaurantes (no se utiliza explícitamente en el proceso de reservas).

4. **TIPORESERVA**:
   - Define diferentes tipos de reserva para clasificarlas según su propósito o requisitos específicos.
   - Atributos: IDTIPORESERVA, TIPO.

5. **RESTAURANTE**:
   - Almacena información sobre los restaurantes disponibles.
   - Atributos: IDRESTAURANTE, NOMBRE, DIRECCION, TELEFONO.

6. **MESA**:
   - Contiene información sobre las mesas disponibles en cada restaurante.
   - Atributos: IDMESA, IDRESTAURANTE, CAPACIDAD, DISPONIBLE.

7. **RESERVA**:
   - Registra las reservas realizadas por los clientes.
   - Atributos: IDRESERVA, IDCLIENTE, IDMESA, IDEMPLEADO, IDTIPORESERVA, FECHA.

### Problemática Resuelta:

Esta base de datos permite gestionar eficientemente el proceso de reserva en restaurantes, desde la información de los clientes y empleados hasta la disponibilidad de mesas y el registro de reservas. Algunos aspectos que aborda incluyen:

- Registro de clientes y empleados involucrados en el proceso de reserva.
- Clasificación de las reservas según su tipo.
- Gestión de la disponibilidad de mesas en cada restaurante.
- Registro detallado de las reservas realizadas, incluyendo la fecha, cliente, mesa, empleado y tipo de reserva.

En resumen, esta base de datos proporciona una estructura para organizar y gestionar eficientemente las operaciones de reserva en restaurantes, lo que contribuye a mejorar el servicio ofrecido a los clientes y optimizar las operaciones del restaurante.
*/

### MEDIOS DE RESERVAS


#### DER SIMPLIFICADO
```
+------------------+        +-----------------------+        +------------------+
|      CLIENTE     |        |       RESERVA         |        |     RESTAURANTE  |
+------------------+        +-----------------------+        +------------------+
| idCliente (PK)   |<>-----o| idReserva (PK)        |o-------| idRestaurante(PK)|
| nombre           |        | idCliente (FK)        |        | nombre           |
| telefono         |        | idMesa (FK)           |        | direccion        |
| correo           |        | idEmpleado (FK)       |        | telefono         |
+------------------+        | idTipoReserva (FK)    |        +------------------+
                            | fecha                 |
                            | cancelacion           |                  |
                            +-----------------------+                  |
                                    |                                  |
                                    |                                  |
                                    v                                  v
+------------------+        +------------------+             +-------------------+
|     Empleado     |        |      Mesa        |             |     Dueno         |
+------------------+        +------------------+             +-------------------+
| idEmpleado (PK)  |        | idMesa (PK)      |             | idDueno (PK)      |
| nombre           |        | idRestaurante(FK)|             | nombre            |
| telefono         |        | capacidad        |             | correo            |
| correo           |        | disponible       |             | telefono          |
| idRestaurante(FK)|        +------------------+             +-------------------+
+------------------+                  |
                             +-------------------+
                             |   TipoReserva     |
                             +-------------------+
                             | idTipoReserva(PK) |
                             | tipo              |
                             +-------------------+
``
