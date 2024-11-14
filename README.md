# Nombre del Proyecto
**RetailPro**

# Descripción del Proyecto
RetailPro es un sistema de gestión diseñado para cualquier supermercado, enfocado en la administración de productos, inventario y ventas diarias. Desarrollado en Java con una interfaz gráfica en Swing, RetailPro se conecta a una base de datos PostgreSQL para almacenar información clave sobre productos y transacciones.

# Objetivos del Proyecto
1. **Gestión de Productos**: Agregar, actualizar, eliminar y consultar productos.
2. **Control de Inventario**: Monitorear las existencias de cada producto.
3. **Registro de Ventas**: Registrar cada venta en el sistema, incluyendo el cajero y el total de la transacción.
4. **Informes y Reportes de Ventas**: Generar reportes básicos de ventas diarias y mensuales.

# Funcionalidades Principales
1. **Gestión de Productos**:
   - Agregar, editar y eliminar productos.
   - Buscar productos por nombre, categoría o código.
   - Registrar precios.

2. **Gestión de Inventario**:
   - Controlar la cantidad disponible de cada producto.

3. **Registro de Ventas**:
   - Registrar ventas con fecha, cajero y lista de productos vendidos.
   - Calcular el total de cada venta.
   - Imprimir tickets de venta.

4. **Generación de Reportes de Ventas**:
   - Generar reportes de ventas diarias, semanales y mensuales para el administrador.

# Tecnologías
- **Lenguaje de Programación**: Java
- **Interfaz Gráfica**: Java Swing
- **Base de Datos**: PostgreSQL (almacenará productos y ventas)
- **Control de Versiones**: GitHub (para colaboración y seguimiento de cambios)

# Estructura de Tablas en PostgreSQL

## Tabla `Producto`
| Campo        | Tipo           | Descripción                      |
|--------------|----------------|----------------------------------|
| id_producto  | SERIAL         | Identificador único del producto |
| nombre       | VARCHAR(100)   | Nombre del producto              |
| categoria    | VARCHAR(50)    | Categoría del producto           |
| precio       | NUMERIC(10, 2) | Precio unitario                  |
| stock        | INT            | Cantidad disponible              |

## Tabla `Venta`
| Campo        | Tipo           | Descripción                      |
|--------------|----------------|----------------------------------|
| id_venta     | SERIAL         | Identificador único de la venta  |
| fecha        | DATE           | Fecha de la venta                |
| id_cajero    | INT            | Identificador del cajero         |
| total        | NUMERIC(10, 2) | Total de la venta                |

## Tabla `DetalleVenta`
| Campo          | Tipo           | Descripción                        |
|----------------|----------------|------------------------------------|
| id_detalle     | SERIAL         | Identificador único del detalle    |
| id_venta       | INT            | Identificador de la venta          |
| id_producto    | INT            | Identificador del producto         |
| cantidad       | INT            | Cantidad vendida                   |
| precio_unitario | NUMERIC(10, 2)| Precio unitario del producto       |

# Asignación de Tareas

1. **Desarrollador 1 - Gestión de Productos e Inventario**:
   - Crear clases para la gestión de productos.
   - Implementar las funcionalidades de agregar, editar, eliminar y consultar productos.
   - Desarrollar el control de inventario.

2. **Desarrollador 2 - Ventas y Reportes**:
   - Implementar la funcionalidad de registro de ventas.
   - Crear el módulo para la generación de reportes de ventas diarias y mensuales.
   - Integrar el sistema de impresión de tickets de venta.

3. **Desarrollador 3 - Base de Datos e Interfaz**:
   - Configurar la base de datos PostgreSQL y establecer la conexión.
   - Desarrollar la interfaz gráfica en Swing.
   - Asegurar la interacción eficiente entre la base de datos y la interfaz de usuario.

# Plan de Desarrollo (3 semanas)

1. **Semana 1**: Configuración del proyecto, creación de la base de datos en PostgreSQL, desarrollo de clases modelo y la interfaz gráfica básica.
2. **Semana 2**: Implementación de los módulos de productos e inventario y conexión de la base de datos.
3. **Semana 3**: Desarrollo del módulo de ventas, generación de reportes, pruebas y depuración final.

# Requerimientos Técnicos
- **Java JDK** versión 8 o superior.
- **Base de Datos PostgreSQL**.
- **IDE Recomendado**: IntelliJ IDEA o Eclipse.
- **Control de Versiones**: GitHub.

---
