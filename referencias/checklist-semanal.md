# ✅ Checklist Semanal del Curso

📁 [Documentación](../README.md) / 📁 [Referencias](README.md) / **Checklist Semanal**

---

Hitos verificables por semana de progresión.

---

## 📅 Semana 1-2: Introducción

- [ ] Entiendes qué es la arquitectura por capas
- [ ] Sabes diferenciar Controller, Flujo, DA, Reglas
- [ ] Has creado una solución .NET 8 básica
- [ ] Comprendes la diferencia entre interfaz e implementación

---

## 📅 Semana 3-4: API Básico

- [ ] El API retorna datos JSON en GET /api/vehiculo
- [ ] POST /api/vehiculo crea registros nuevos (retorna 201)
- [ ] PUT /api/vehiculo/{id} actualiza registros (retorna 200)
- [ ] DELETE /api/vehiculo/{id} elimina registros (retorna 204)
- [ ] Swagger funciona y documenta todos los endpoints

**Control de calidad:**
- [ ] Solo hay un Guid.NewGuid() por entidad (en DA, no en controller)
- [ ] Flujo no accede a bases de datos directamente
- [ ] Nombres en español (Obtener, Agregar, Editar)

---

## 📅 Semana 5: Frontend Web + React

### Web (Razor Pages)

- [ ] Página Index lista vehículos desde el API
- [ ] Página Agregar crea vehículos nuevos
- [ ] Página Editar actualiza registros existentes
- [ ] Página Detalle muestra información completa
- [ ] Eliminación funciona correctamente

### React

- [ ] Proyecto React abierto en localhost:5173
- [ ] Página de lista muestra vehículos del API
- [ ] Creación, edición, eliminación funcionan  
- [ ] Sin reloads de página en las transiciones
- [ ] Tailwind aplicado a componentes

**Control:**
- [ ] React usa `useEffect` para cargar datos
- [ ] Los hooks manejan state (`useState`)
- [ ] TypeScript: todas las variables tienen tipos

---

## 📅 Semana 6: Seguridad

- [ ] Login funciona (POST /conta/login → JWT)
- [ ] API requiere Bearer token: `[Authorize]`
- [ ] Los controllers retornan `401` si NO hay token
- [ ] Retorna `403` si el rol es incorrecto
- [ ] WEB Razor mantiene sesión en cookie

**Control:**
- [ ] Las contraseñas se hash-ean (SHA256) antes de enviar
- [ ] El JWT tiene claims (Name, Email, Role)
- [ ] Logout destruye la cookie

---

## 📅 Semana 7: Validaciones

- [ ] Los modelos tienen validaciones (DataAnnotations)
- [ ] Email: `[EmailAddress]` 
- [ ] Teléfono: `[Phone]`
- [ ] Placa: `[RegularExpression(@"[A-Za-z]{3}-[0-9]{3}")]`
- [ ] Los errores se muestran en la UI

---

## 📅 Semana 8-9: Base de Datos Avanzada

- [ ] Todas las operaciones usan Stored Procedures
- [ ] Los SPs retornan el GUID de la entidad
- [ ] Joins funcionan (tabla Vehiculo + Marca + Modelo)
- [ ] Las consultas son eficientes (sin N+1)

---

## 📅 Semana 10-11: Servicios Externos

- [ ] Servicios HTTP llaman a APIs externas
- [ ] Reglas usan Servicios (NO acceso directo)
- [ ] Los endpoints de Revision y Registro responden
- [ ] VehiculoDetalle incluye `revisionValida` y `registroValido`

---

## 📅 Semana 12-13: Testing y Despliegue

- [ ] Los tests unitarios cubren al menos un Use Case
- [ ] GitHub Actions publica automáticamente
- [ ] Los 3 proyectos están en Azure
- [ ] Las variables de entorno están configuradas

**URLs en producción:**
- [ ] API: `https://nombreapi.azurewebsites.net/api/vehiculo`
- [ ] WEB: `https://nombrew eb.azurewebsites.net`
- [ ] React: `https://nombrereact.azurewebsites.net`

---

## 📅 Semana 14: Integración Completa

- [ ] Los 3 frontends se comunican con el API central
- [ ] CORS está correctamente configurado
- [ ] Seguridad funciona en todos los proyectos
- [ ] La BD está sincronizada entre desarrollos y producción
- [ ] Migraciones de schema son automáticas

---

## 🎯 Objetivos finales

- [ ] El código sigue las convenciones del curso (español, patrones)
- [ ] Todos los endpoints están documentados en Swagger
- [ ] No hay warnings de compilación ni errores de análisis estático
- [ ] El README explica cómo correr el proyecto localmente
- [ ] Las instrucciones de deployment son claras

---

## 📊 Escala de completitud

| % | Estado | Acción |
|---|--------|--------|
| 0-25% | Muy atrás | Revisita las semanas 1-4 |
| 26-50% | Atrasado | Enfócate en API base |
| 51-75% | En tiempo | Continúa con seguridad |
| 76-90% | Adelantado | Optimiza y deploya |
| 91-100% | Completado | Entrega y retroalimentación |

---

*Checklist del Curso SC701 — Ajusta según tu progresión*
