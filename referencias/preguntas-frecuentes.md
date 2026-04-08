# ❓ Preguntas Frecuentes (FAQ)

Respuestas ágiles a dudas comunes durante el curso.

---

## 🔐 Seguridad

### ¿Por qué `[Authorize]` en la clase y también en cada método?

**Respuesta:** 
- `[Authorize]` en la clase: requiere autenticación para TODO
- `[Authorize(Roles = "1")]` en métodos: requiere rol específico
- Sin ambos, algunos métodos podrían saltarse la seguridad

### ¿El JWT se envía en cada petición?

**Respuesta:** Sí. El navegador lo envía automáticamente en el header:
```
Authorization: Bearer eyJhbGciOiJIUzI1NiIs...
```

### ¿Qué pasa si el JWT expira durante una sesión?

**Respuesta:**
1. Servidor retorna `401 Unauthorized`
2. Cliente debería redirigir al login
3. El usuario se autentica de nuevo y obtiene un JWT fresco

---

## 🌐 Frontend vs Backend

### ¿Por qué React es más rápido que Razor Pages?

**Respuesta:**
- React: una descarga inicial de JS, luego cambios en memoria (sin reload)
- Razor: cada acción = nueva petición HTTP + nuevo render del servidor
- Trade-off: React es más complejo de desarrollar

### ¿Mi WEB (Razor) necesita CORS?

**Respuesta:**
- Si (WEB + API) están en el mismo origen: **NO**
- Si están en orígenes diferentes: **SÍ**, configura CORS en el API

---

## 🗄️ Base de Datos

### ¿Puedo usar INT como clave primaria en lugar de GUID?

**Respuesta:** 
- INT: más pequeño (4 bytes), auto-increment, predecible
- GUID: 16 bytes, único globalmente, está en el curso
- En este curso: **usa GUID** (es el estándar asignado)

### ¿Es obligatorio usar Stored Procedures?

**Respuesta:**
- En este curso: **SÍ**, todos los DAs usan SPs
- Ventajas: reutilización, validación en BD, seguridad
- Con Dapper: `connection.QueryAsync<T>("NombreSP")`

---

## 🏗️ Arquitectura

### ¿La capa Reglas llama a DA directamente?

**Respuesta:** **NO**. Siempre a través de Servicios:
```
Reglas → Servicios → API Externo
Reglas NO → DA (eso es responsabilidad de Flujo)
```

### ¿Todos los métodos deben ser `async`?

**Respuesta:** En este curso, **SÍ**:
- Controllers: `async Task<IActionResult>`
- Flujo: `async Task<T>`
- DA: `async Task<T>`

---

## 📦 Deployment

### ¿GitHub Actions se dispara automáticamente?

**Respuesta:**
- Sí, cuando haces `git push` a la rama `main`
- Si el `.yml` está configurado con `on: [push]`
- Puedes verlo en la pestaña "Actions" del repo

### ¿Cómo sé si el deploy falló?

**Respuesta:**
1. GitHub Actions → pestaña "Actions"
2. Busca el workflow y haz clic
3. Revisa los logs en rojo (errores)
4. Azure → App Service → Kudu (https://app.scm.azurewebsites.net)

---

## 🔧 Troubleshooting General

### "401 Unauthorized" en Swagger

**Causa:** No pasaste el token
**Solución:** 
1. Haz login para obtener token
2. Clic en 🔓 Authorize
3. Pega el `AccessToken`

### "CORS Error"

**Causa:** El frontend intenta acceder a API en origen diferente
**Solución:** En `Program.cs` del API:
```csharp
builder.Services.AddCors(options =>
    options.AddPolicy("MiPolicy", policy =>
        policy.WithOrigins("https://localhost:5173")
              .AllowAnyHeader()
              .AllowAnyMethod()
    )
);
```

### NullReferenceException en clases

**Causa común:** Variable no inicializada
**Debug:** Agrega breakpoint y inspecciona valores

---

## 📚 Estudio y Aprendizaje

### ¿Cuál es el mejor orden para estudiar?

**Recomendación:**
1. **Semana 2-3:** Estructura básica del API (capas, interfaces)
2. **Semana 4:** Parámetros en routes, servicios, reglas
3. **Semana 5:** Frontend (WEB y React)
4. **Semana 6:** Seguridad (JWT, autenticación)
5. **Semana 7+:** Despliegue, optimización

### ¿Necesito memorizar todo el código?

**Respuesta:** **NO**. Entiende los patrones:
- Cómo fluye la data (request → controller → flujo → da → db)
- Cómo se protegen los endpoints (`[Authorize]`)
- Cómo se comunica el frontend con el backend

---

*FAQ del Curso SC701 — Actualizado regularmente con preguntas reales*
