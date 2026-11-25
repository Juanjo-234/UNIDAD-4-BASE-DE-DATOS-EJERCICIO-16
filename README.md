# UNIDAD-4-BASE-DE-DATOS-EJERCICIO-16
1. Entidades Principales y Personas
propietario

Almacena los datos de los dueños de los inmuebles.

Atributos: dni_cuit (clave primaria), nombre, apellido, telefono y correo.

inquilino

Registra la información de los arrendatarios o clientes que alquilan las propiedades.

Atributos: dni_cuit (clave primaria), nombre, apellido, telefono y correo.

empleado

Controla al personal de la inmobiliaria encargado de gestionar las operaciones.

Atributos: id_legajo (clave primaria), cargo, nombre, apellido y correo.

2. Gestión de Inmuebles y Contratos
propiedad

Contiene el catálogo de bienes raíces administrados por la inmobiliaria.

Atributos: id_propiedad (clave primaria), codigo_catastral (con restricción única), ciudad, superficie, cantidad_habitantes, direccion y dni_cuit_propietario (clave foránea hacia propietario).

contrato

Administra los acuerdos legales de alquiler formalizados entre las partes.

Atributos: id_contrato (clave primaria), fecha_inicio, fecha_fin, monto, deposito_garantia, id_legajo (clave foránea al empleado gestor), dni_cuit_inquilino (clave foránea al inquilino) e id_propiedad (clave foránea a la propiedad).

3. Registro de Transacciones Financieras
pago

Registra las cuotas o montos abonados correspondientes a los contratos vigentes.

Atributos: id_pago (clave primaria), medio_pago, recargo_demora (con valor por defecto en 0), periodo_abonado, monto_abonado, id_contrato, dni_cuit_inquilino e id_propiedad (claves foráneas que garantizan la trazabilidad del pago).

IMAGEN DE EJEMPLO DE UNA CONSULTA:
<img width="1305" height="362" alt="image" src="https://github.com/user-attachments/assets/58a4a9ee-d1df-4b40-afcf-c3e1fff3ab1f" />


4. Restricciones e Integridad Referencial (Foreign Keys)
El script configura de manera estricta las reglas de validación para asegurar la consistencia relacional mediante claves primarias, claves únicas y claves foráneas que vinculan propiedades con propietarios, contratos con empleados, inquilinos y propiedades, y pagos con sus respectivos contratos.
