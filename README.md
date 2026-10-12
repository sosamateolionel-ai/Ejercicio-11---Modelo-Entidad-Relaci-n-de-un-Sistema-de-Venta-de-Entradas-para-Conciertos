# Ejercicio 11 - Modelo Entidad-Relación de un Sistema de Venta de Entradas para Conciertos

## Descripción
Este ejercicio consiste en diseñar un modelo Entidad-Relación (DER) para un sistema de venta de entradas y gestión de eventos musicales. El modelo permite administrar recintos, sectores, conciertos, tickets, clientes y transacciones de compra.

## Entidades y atributos

### 1. Recinto
Representa los espacios físicos, estadios o auditorios donde se realizan los eventos.
- **id_recinto**: identificador único del recinto.
- **nombre**: nombre del recinto.
- **direccion**: ubicación física.
- **ciudad**: ciudad donde se encuentra.
- **capacidad total**: aforo máximo del recinto.

### 2. Sector
Representa las distintas zonas o ubicaciones dentro de un recinto (ej. platea, campo, pullman).
- **id_recinto**: identificador del recinto al que pertenece.
- **id_sector**: identificador único del sector.
- **nombre**: nombre del sector.
- **cantidad**: cantidad de lugares disponibles en el sector.
- **precio base**: tarifa inicial de las ubicaciones del sector.

### 3. Concierto
Representa los eventos musicales programados.
- **id_concierto**: identificador único del concierto.
- **id_recinto**: identificador del recinto donde se lleva a cabo.
- **titulo**: título o nombre del evento.
- **artista**: artista o banda principal.
- **estado**: estado actual del concierto (ej. programado, finalizado, suspendido).
- **fecha hora**: fecha y hora de realización.

### 4. Ticket
Representa las entradas individuales emitidas para los conciertos.
- **id_ticket**: identificador único del ticket.
- **nro compra**: número de orden o compra asociada.
- **id_concierto**: identificador del concierto al que da acceso.
- **id_sector**: identificador del sector correspondiente.
- **estado**: estado del ticket (ej. disponible, vendido, usado).
- **precio final**: costo definitivo de la entrada.

### 5. Cliente
Representa a los usuarios registrados en la plataforma para adquirir entradas.
- **id_cliente**: identificador único del cliente.
- **dni**: documento de identidad.
- **nombre**: nombre completo del cliente.
- **email**: correo electrónico.
- **numero**: número de teléfono de contacto.
- **contraseña**: credencial de acceso al sistema.

### 6. Compra
Representa la transacción económica realizada por los clientes para adquirir sus tickets.
- **id_compra**: identificador único de la compra.
- **id_ticket**: identificador del ticket adquirido.
- **fecha hora**: marca temporal de la transacción.
- **pago**: método o medio de pago utilizado.
- **estado pago**: estado de la transacción (ej. aprobado, pendiente, rechazado).

## Relaciones y cardinalidades
- **Recinto – Sector (Tiene / 1:N)**: un recinto está compuesto por múltiples sectores diferenciados.
- **Recinto – Concierto (Contiene / 1:N)**: un recinto aloja diversos conciertos a lo largo del tiempo.
- **Sector – Ticket (Genera / 1:N)**: un sector da origen a la emisión de múltiples tickets de entrada.
- **Concierto – Ticket (Necesita / 1:N)**: un concierto requiere la generación y venta de entradas (tickets) para los asistentes.
- **Ticket – Compra (Vende / 1:N)**: los tickets son comercializados a través de los registros de compra.
- **Cliente – Compra (De / 1:N)**: un cliente puede realizar una o más transacciones de compra de entradas.

## Objetivo
Diseñar una base de datos para una plataforma de venta de entradas que permita organizar la infraestructura de recintos y sectores, programar conciertos, administrar la disponibilidad de tickets por zona y controlar de forma segura el registro de clientes y sus transacciones de compra.
