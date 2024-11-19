# Retrofit

## 1. Agregar dependencias
- Retrofit
- Conversores (Gson, Moshi, etc.)

## 2. Configurar Retrofit
- Crear un cliente con `Retrofit.Builder`
- Establecer URL base y convertidor

## 3. Definir la interfaz de la API
- Declarar endpoints con anotaciones (`@GET`, `@POST`, etc.)
- Especificar parámetros y respuestas

## 4. Crear instancia de la API
- Utilizar `retrofit.create(Interface::class.java)`

## 5. Llamar al servicio
- Usar coroutines o `Call` para manejar las respuestas
- Procesar datos recibidos o manejar errores
