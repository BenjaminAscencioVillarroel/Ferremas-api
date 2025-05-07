# API Ferremás

## Descripción

Esta es una API para la gestión de productos y sucursales de la tienda **Ferremás**. La API permite realizar operaciones CRUD sobre productos y sucursales, asociar productos a sucursales y realizar filtros en los productos. Está desarrollada utilizando **Java** y **Spring Boot**.

## Requisitos

Antes de comenzar, asegúrate de tener instalados los siguientes programas:

- **Java 17 o superior**.
- **Postman** (para probar la API).

## Pasos para ejecutar el proyecto

### 1. Clonar o descargar el proyecto

2. Importar la colección de Postman
Para probar la API, necesitas importar la colección de Postman que contiene todas las solicitudes preconfiguradas. Haz lo siguiente:

Abre Postman.

Ve a File > Import.

Selecciona el archivo api_ferremas_collection.json desde la carpeta /postman del proyecto.

o si prefieres arrastra el archivo hacia el Postman

La colección se importará y aparecerá en tu Postman, donde podrás ver los diferentes endpoints configurados.

3. Ejecutar la API en modo Run and Debug
Para ejecutar la API, puedes usar cualquier IDE compatible con Java, como IntelliJ IDEA o Visual Studio Code.

Haz clic en el botón Run para ejecutar el proyecto.

La API se ejecutará en el puerto 8080, y podrás acceder a ella en http://localhost:8080.

4. Probar la API en Postman
Una vez que la API esté ejecutándose, podrás probar los endpoints en el siguiente orden utilizando Postman:

Paso 1: Crear una Sucursal
En Postman, selecciona la solicitud POST /sucursales.

En el cuerpo de la solicitud (body, raw, json), ingresa el siguiente JSON para crear una sucursal:

{
  "nombre": "Sucursal Centro",
  "direccion": "Av. Principal 123, Ciudad"
}
Haz clic en Send y verifica que se haya creado correctamente la sucursal.

Paso 2: Crear un Producto
Ahora, selecciona la solicitud POST /productos en Postman.

En el cuerpo de la solicitud, ingresa el siguiente JSON para crear un producto y asociarlo a la sucursal que creaste en el paso anterior (por ejemplo, Sucursal con id: 1):

json
Copiar
Editar
{
  "nombre": "Martillo de acero",
  "categoria": "herramientas",
  "precio": 45.99,
  "stock": 30,
  "sucursales": [
    { "id": 1 }
  ]
}
Haz clic en Send y asegúrate de que el producto se haya creado correctamente y esté asociado a la sucursal.

Paso 3: Consultar Productos por Sucursal
Para verificar que el producto está correctamente asociado a la sucursal, selecciona la solicitud GET /sucursales/{id}/productos en Postman.

Ingresa el ID de la sucursal que creaste (por ejemplo, 1).

Haz clic en Send para obtener la lista de productos disponibles en esa sucursal.

Paso 4: Probar otros endpoints
GET /productos: Lista todos los productos o aplica filtros.

GET /productos/{id}: Obtiene un producto por su ID.

PUT /productos/{id}: Reemplaza todos los campos de un producto.

PATCH /productos/{id}: Actualiza parcialmente un producto.

DELETE /productos/{id}: Elimina un producto.

6. Finalización
¡Listo! Ahora deberías tener tu API corriendo y funcionando correctamente, y puedes probar los distintos endpoints utilizando la colección de Postman.