# **Proyecto: RetailPro**

## **Descripción del Proyecto**  
RetailPro es un sistema completo de gestión para supermercados, diseñado para manejar productos, inventarios, ventas, usuarios y clientes en un entorno real. Además, incluye la generación de reportes y facturación básica. El sistema será desarrollado en **Java** utilizando **Swing** para la interfaz gráfica, con **PostgreSQL** como base de datos.

---

## **Objetivos del Proyecto**
1. **Gestión de Productos:** CRUD (Crear, Leer, Actualizar, Eliminar) de productos con control de precios, categorías y existencias.  
2. **Gestión de Usuarios:** Permitir la administración de roles (cajeros y administradores) con diferentes niveles de acceso.  
3. **Gestión de Clientes:** Registrar información básica de los clientes para asociar compras y emitir facturas.  
4. **Registro y Facturación de Ventas:** Registrar cada venta con detalles completos y emitir un ticket/factura.  
5. **Control de Inventarios:** Monitorear existencias y alertar sobre productos con bajo stock.  
6. **Reportes:** Generar informes detallados de ventas diarias, semanales, mensuales y estadísticas por producto y cliente.

---

## **Funcionalidades Principales**

### **1. Gestión de Productos**
- Registro de productos con datos clave: nombre, categoría, precio, stock mínimo y máximo.  
- Búsqueda de productos por nombre, categoría o código de barras.  
- Alerta visual cuando el stock sea menor al mínimo configurado.  

### **2. Gestión de Usuarios**
- Roles:  
  - **Administrador:** Acceso completo al sistema.  
  - **Cajero:** Acceso limitado al módulo de ventas y consulta de productos.  
- Funciones de agregar, editar y deshabilitar usuarios.  
- Registro de auditoría para rastrear actividades.  

### **3. Gestión de Clientes**
- Registro de clientes con datos básicos: nombre, teléfono, correo electrónico y dirección.  
- Asociación de compras para generar facturas con datos del cliente.  

### **4. Registro y Facturación de Ventas**
- Ventana de ventas interactiva para:
  - Selección de productos y cantidades.  
  - Cálculo automático del total.  
  - Emisión de ticket o factura (formato PDF).  
- Actualización automática del inventario tras cada venta.  

### **5. Reportes y Estadísticas**
- **Reportes de Ventas:**
  - Diarias, semanales y mensuales.  
  - Ventas por cajero y por cliente.  
- **Inventarios:** Productos con bajo stock y estadísticas de rotación.  
- **Clientes:** Registro de los clientes con mayores compras.  

---

## **Estructura de Tablas en PostgreSQL**

### **Tabla Producto**  
| Campo          | Tipo            | Descripción                  |  
|----------------|-----------------|------------------------------|  
| id_producto    | SERIAL          | Identificador único          |  
| nombre         | VARCHAR(100)    | Nombre del producto          |  
| categoria      | VARCHAR(50)     | Categoría del producto       |  
| precio         | NUMERIC(10, 2)  | Precio unitario             |  
| stock          | INT             | Cantidad en inventario       |  
| stock_minimo   | INT             | Stock mínimo permitido       |  

### **Tabla Usuario**  
| Campo         | Tipo            | Descripción                  |  
|---------------|-----------------|------------------------------|  
| id_usuario    | SERIAL          | Identificador único          |  
| nombre        | VARCHAR(50)     | Nombre del usuario           |  
| rol           | VARCHAR(20)     | Rol del usuario (cajero/admin)|  
| username      | VARCHAR(50)     | Nombre de usuario            |  
| password      | VARCHAR(255)    | Contraseña                   |  

### **Tabla Cliente**  
| Campo         | Tipo            | Descripción                  |  
|---------------|-----------------|------------------------------|  
| id_cliente    | SERIAL          | Identificador único          |  
| nombre        | VARCHAR(100)    | Nombre del cliente           |  
| telefono      | VARCHAR(15)     | Teléfono                     |  
| email         | VARCHAR(50)     | Correo electrónico           |  
| direccion     | VARCHAR(255)    | Dirección del cliente        |  

### **Tabla Venta**  
| Campo         | Tipo            | Descripción                  |  
|---------------|-----------------|------------------------------|  
| id_venta      | SERIAL          | Identificador único          |  
| fecha         | TIMESTAMP       | Fecha y hora de la venta     |  
| id_cajero     | INT             | Identificador del cajero     |  
| total         | NUMERIC(10, 2)  | Total de la venta            |  
| id_cliente    | INT             | Cliente asociado (opcional)  |  

### **Tabla DetalleVenta**  
| Campo         | Tipo            | Descripción                  |  
|---------------|-----------------|------------------------------|  
| id_detalle    | SERIAL          | Identificador único          |  
| id_venta      | INT             | Identificador de la venta    |  
| id_producto   | INT             | Identificador del producto   |  
| cantidad      | INT             | Cantidad vendida             |  
| precio_unitario | NUMERIC(10, 2)| Precio unitario del producto |  

---

## **División de Tareas**

### **Desarrollador 1 - Backend y Base de Datos**
- Configuración de la base de datos PostgreSQL.  
- Desarrollo de clases de negocio: productos, usuarios, clientes, ventas e inventarios.  

### **Desarrollador 2 - Interfaz Gráfica**
- Diseño de pantallas en Swing para productos, ventas, usuarios y reportes.  
- Integración con el backend para operaciones CRUD.  

### **Desarrollador 3 - Reportes y Facturación**
- Implementación de reportes de ventas y estadísticas en tablas y gráficos.  
- Generación de tickets/facturas en PDF.  
- Pruebas y validación final del sistema.  

---

## **Cronograma**

### **Semana 1:**
- Configuración del entorno, diseño de la base de datos y desarrollo de clases modelo.  
- Creación de pantallas para productos y usuarios.  

### **Semana 2:**
- Finalización del módulo de inventarios y ventas.  
- Conexión entre la interfaz gráfica y la base de datos.  

### **Semana 3:**
- Desarrollo de reportes, facturación y validación de funcionalidades.  
- Pruebas y depuración final.  

---

## **Entregables Finales**
1. Código fuente y documentación del sistema.  
2. Base de datos exportada.  
3. Sistema ejecutable en `.jar`.  
4. Manual de usuario.  
