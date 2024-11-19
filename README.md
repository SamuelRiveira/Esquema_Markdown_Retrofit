# Retrofit
## ¿Qué es Retrofit?
- Biblioteca de cliente HTTP para Android y Java.
- Facilita la comunicación con APIs RESTful.
- Transforma automáticamente respuestas JSON/XML en objetos.

## Principales características
- **Mapeo automático:** Convierte respuestas JSON/XML en POJOs.
- **Basado en interfaces:** Declaración de endpoints como métodos de una interfaz.
- **Interceptors:** Para modificar peticiones o respuestas.
- **Integración con Gson/Moshi:** Manejo de serialización/deserialización.
- **Soporte para coroutines:** Fácil manejo de llamadas asíncronas en Kotlin.

## Arquitectura de Retrofit
1. **Retrofit.Builder:**
   - Configura la instancia de Retrofit.
   - Define la URL base.
   - Asigna convertidores como Gson o Moshi.
2. **Interfaz de la API:**
   - Define métodos HTTP (`@GET`, `@POST`, etc.).
   - Especifica endpoints y parámetros.
3. **Convertidores:**
   - Transforman datos JSON/XML en objetos Java/Kotlin.
4. **Adaptadores de llamadas:**
   - Soporte para RxJava, coroutines o `Call`.
5. **Cliente HTTP:**
   - Generalmente usa OkHttp como backend.

## Ejemplo básico de Retrofit
### Paso 1: Agregar dependencias
```gradle
implementation 'com.squareup.retrofit2:retrofit:<version>'
implementation 'com.squareup.retrofit2:converter-gson:<version>'
```
### Paso 2: Crear interfaz de la API
```kotlin
interface ApiService {
    @GET("users")
    suspend fun getUsers(): List<User>
}
```
### Paso 3: Configurar Retrofit
```kotlin
val retrofit = Retrofit.Builder()
    .baseUrl("https://api.example.com/")
    .addConverterFactory(GsonConverterFactory.create())
    .build()

val api = retrofit.create(ApiService::class.java)
```
### Paso 4: Realizar llamadas
```kotlin
val users = api.getUsers()
```
