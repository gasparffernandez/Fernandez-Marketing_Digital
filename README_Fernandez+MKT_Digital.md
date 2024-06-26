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
   - Almacena la información de los clientes que utilizan los servicios de alocación de marketing digital.
   - Atributos: IDCLIENTE, NOMBRE, TELEFONO, MAIL, DIRECCION.

2. **EMPLEADO**:
   - Contiene los datos de los empleados involucrados en la gestión de presupuestos, ventas y atención al cliente.
   - Atributos: IDEMPLEADO, CARGO, NOMBRE, TELEFONO, MAIL.

3. **TIPOSERVICIO**:
   -  Clasifica los servicios ofrecidos según nivel de personalización.
   -  Atributos: IDTIPOSERVICIO, NOMBRE, DESCRIPCION, COMENTARIO.

4. **SERVICIO**:
   - Detalla los servicios específicos ofrecidos a los clientes.
   - Atributos: IDSERVICIO, IDTIPOSERVICIO, FECHA, DESCRPCION.

5. **PLATAFORMA_MKT**:
   - Almacena información sobre las plataformas donde se realizarán las campañas de marketing digital.
   - Atributos: IDPLATAFORMA, NOMBRE, DESCRIPCION, ESTADO_SATURACION.

6. **ASIGNACION_PRESUPUESTO**:
   - Contiene información sobre la asociación de los clientes con las plataformas específicas y el monto de presupuesto asignado.
   - Atributos: IDASIGNACION, IDCLIENTE, IDPLATAFORMA, FECHA, MONTO.

7. **VENTA**:
   - Registra cada transacción de venta realizada a través de la aplicación.
   - Atributos: IDVENTA, IDCLIENTE, IDSERVICIO, IDEMPLEADO, FECHA, COMENTARIO.

8. **COBRO**:
   - Registra cada transacción de cobro relacionada con las ventas realizadas.
   - Atributos: IDCOBRO, IDVENTA, IDCLIENTE, IDEMPLEADO, FECHA, COMENTARIO.

9. **PERFORMANCE_PLATAFORMAS**:
   - Registra métricas de rendimiento de cada plataforma de marketing (datos clave sobre el rendimiento de cada plataforma a lo largo del tiempo, permitiendo evaluar la efectividad de las campañas).
   - Atributos: IDPERFORMANCE_PLATAFORMA , IDPLATAFORMA, METRICA, FECHA, 

10. **FORMA_COBRO**:
   - Define las formas específicas de cobro registrados en el sistema.
   - Atributos: IDFORMA_COBRO, IDCOBRO, COMENTARIO.

11. **HISTORIAL_COBRO**:
   - Registra el historial detallado de cada cobro realizado.
   - Atributos: IDHISTORIAL_COBRO, IDCOBRO, IDFORMA_COBRO, IDEMPLEADO, COMENTARIO.

### Problemática Resuelta:

Esta base de datos permite gestionar eficientemente la alocación del marketing digital, abordando diversos aspectos cruciales para optimizar la distribución de presupuestos en plataformas digitales. Algunos puntos clave que abarca incluyen:

- Registro de clientes y empleados involucrados en el proceso de la alocación.
- Gestión de tipo de servicio.
- Gestión de plataforma de Marketing Digital.
- Registro detallado de las ventas realizadas.
- Registro detallado de los cobros realizados.

En resumen, esta base de datos proporciona una estructura integral para gestionar de manera eficiente y escalable la alocación del marketing digital. Facilita la toma de decisiones estratégicas, mejora la efectividad de las campañas y contribuye a optimizar el retorno de inversión al evitar la saturación de canales.
*/

``
