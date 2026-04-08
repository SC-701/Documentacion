# 📚 Glosario Técnico

📁 [Documentación](../README.md) / 📁 [Referencias](README.md) / **Glosario Técnico**

---

Términos técnicos en español e inglés, con definiciones claras y ejemplos.

---

## A

**API** (Application Programming Interface)
- **ES:** Interfaz de Programación de Aplicaciones
- **Uso:** "El API de vehículos retorna datos en JSON"
- **Ejemplo:** REST API, GraphQL API, SOAP API

**Async/Await**
- **ES:** Asíncrono/Esperar
- **Uso:** Programación no-bloqueante en C#
- **Ejemplo:** `async Task<List<T>> ObtenerAsync()`

**Autenticación**
- **ES:** Verificación de identidad
- **Uso:** Confirmar quién eres (login)
- **Contraste:** Autorización = qué puedes hacer

---

## B

**Backend**
- **ES:** Sistema trasero / servidor
- **Uso:** Lógica de negocio, BD, APIs
- **Contraste:** Frontend = lo que ve el usuario

**Bearer Token**
- **ES:** Token portador
- **Uso:** `Authorization: Bearer <token>` en headers HTTP
- **Ejemplo:** JWT en formato `eyJ...`

**BindProperty**
- **ES:** Propiedad vinculada
- **Uso:** `[BindProperty] public string Nombre { get; set; }`
- **Contexto:** Razor Pages

---

## C

**CORS** (Cross-Origin Resource Sharing)
- **ES:** Intercambio de Recursos entre Orígenes Cruzados
- **Uso:** Permitir requests desde frontend diferente al backend
- **Configuración:** `WithOrigins("https://localhost:5173")`

**Claims**
- **ES:** Afirmaciones sobre el usuario
- **Uso:** Name, Email, Role (info. dentro del JWT)
- **Tipo:** `ClaimTypes.Name`, `ClaimTypes.Email`, `ClaimTypes.Role`

**Cookie**
- **ES:** Galleta (archivo temporal del navegador)
- **Uso:** Guardar token JWT de forma automática
- **Envío:** Navegador lo incluye en cada petición HTTP

---

## D

**DAO/DA** (Data Access Object / Data Access)
- **ES:** Capa de Acceso a Datos
- **Uso:** Queries a BD, Stored Procedures
- **Nombre en proyecto:** `VehiculoDA`, `MarcaDA`

**Dapper**
- **ES:** ORM ligero para .NET
- **Uso:** `QueryAsync<T>()`, `ExecuteScalarAsync<T>()`
- **Ventaja:** Muy rápido, control total de SQL

**Dependency Injection (DI)**
- **ES:** Inyección de Dependencias
- **Uso:** `AddScoped<IVehiculo, VehiculoDA>()`
- **Beneficio:** Desacoplamiento, testeo fácil

---

## E

**Entity**
- **ES:** Entidad
- **Uso:** Objeto del dominio (Vehiculo, Marca, Modelo)
- **BD:** Corresponde a una tabla

**Endpoint**
- **ES:** Punto de extremo
- **Uso:** URL + método HTTP (GET /api/vehiculo)
- **Tipo:** GET, POST, PUT, DELETE, PATCH

---

## F

**Frontend**
- **ES:** Sistema frontal / cliente
- **Tipo:** Web (React, Razor Pages), Mobile, Desktop
- **Contraste:** Backend = servidor

**Foreign Key (FK)**
- **ES:** Clave Foránea
- **Uso:** Relación entre tablas
- **Ejemplo:** `IdModelo` en tabla `Vehiculo` →  referencia a `Modelo.Id`

---

## G

**GUID** (Globally Unique Identifier)
- **ES:** Identificador Único Global
- **Formato:** `12345678-90ab-cdef-1234-567890abcdef`
- **Uso:** Claves primarias en BD
- **Generación:** `Guid.NewGuid()`

---

## H

**Hash**
- **ES:** Resumen criptográfico
- **Uso:** Proteger contraseñas
- **Algoritmo:** SHA256 → 64 caracteres hexadecimales
- **Propiedad:** Irreversible

**HTTP** (HyperText Transfer Protocol)
- **ES:** Protocolo de Transferencia de Hipertexto
- **Versión segura:** HTTPS (con TLS/SSL)
- **Métodos:** GET, POST, PUT, DELETE, PATCH

**HttpClient**
- **ES:** Cliente HTTP
- **Uso:** Hacer requests HTTP desde .NET
- **Patrón:** `new HttpClient()` o `IHttpClientFactory`

---

## I

**Interface/Interfaz**
- **ES:** Contrato de métodos públicos
- **Naming:** `IVehiculo`, `IVehiculoDA`, `IVehiculoFlujo`
- **Ventaja:** Desacoplamiento, inyección de dependencias

**Issuer**
- **ES:** Emisor (de tokens)
- **Uso:** Quién genera el JWT
- **Config:** `Token:Issuer` en `appsettings.json`

---

## J

**JSON** (JavaScript Object Notation)
- **ES:** Notación de Objetos JavaScript
- **Formato:** `{ "id": 1, "nombre": "Toyota" }`
- **Uso:** Intercambio de datos en APIs

**JWT** (JSON Web Token)
- **ES:** Token Web JSON
- **Estructura:** Header.Payload.Signature (3 partes en base64)
- **Uso:** Autenticación stateless

---

## M

**Middleware**
- **ES:** Software intermedio
- **Uso:** Procesa requests antes de llegar al controller
- **Orden:** `UseAuthentication` → `UseAuthorization`

**Model Binding**
- **ES:** Vinculación de Modelos
- **Uso:** ASP.NET Core mapea JSON → clase C#
- **Automático:** `[FromBody]`, `[FromRoute]`, `[FromQuery]`

---

## N

**NuGet**
- **ES:** Gestor de paquetes para .NET
- **Uso:** `dotnet add package {nombre}`
- **Fuente:** nuget.org o GitHub Packages

---

## O

**ORM** (Object-Relational Mapping)
- **ES:** Mapeo Objeto-Relacional
- **Tipo en curso:** Dapper (ligero), Entity Framework (completo)
- **Uso:** Convertir filas SQL → objetos C#

---

## P

**PageModel**
- **ES:** Modelo de Página
- **Uso:** Code-behind de Razor Pages (.cshtml.cs)
- **Métodos:** `OnGet()`, `OnPost()`, `OnPut()`, `OnDelete()`

**Primary Key (PK)**
- **ES:** Clave Primaria
- **Uso:** Identificador único de fila
- **Tipo en curso:** GUID (no int)

---

## R

**REST** (Representational State Transfer)
- **ES:** Transferencia de Estado Representacional
- **Principios:** Recursos (URIs), Métodos HTTP, Stateless
- **Ejemplo:** `GET /api/vehiculos`, `POST /api/vehiculos`

**Role** (Rol)
- **ES:** Función o rol del usuario
- **Uso:** Admin, Usuario, Moderador
- **Implementación:** `[Authorize(Roles = "1")]`

---

## S

**Scoped**
- **ES:** Alcance por request
- **Uso:** `AddScoped<IVehiculo, VehiculoDA>()`
- **Lifetime:** Se crea una instancia por HTTP request

**SHA256** (Secure Hash Algorithm)
- **ES:** Algoritmo de Hash Seguro 256 bits
- **Longitud:** 64 caracteres hexadecimales
- **Uso:** Hashing de contraseñas

**Stored Procedure**
- **ES:** Procedimiento Almacenado
- **Uso:** SQL pregrabado en BD
- **Nombre:** `AgregarVehiculo`, `ObtenerVehiculos`
- **Ventaja:** Reutilizable, eficiente, validación en BD

---

## T

**Token**
- **ES:** Símbolo o muestra
- **Uso:** Prueba de autenticación (JWT, Bearer)
- **Tipo:** Temporal, con expiración

**TypeScript**
- **ES:** Lenguaje tipado basado en JavaScript
- **Uso:** React + tipos estáticos
- **Sintaxis:** `interface`, `type`, `enum`

---

## V

**View**
- **ES:** Vista
- **Tipo en Razor:** `.cshtml` (HTML + C# embebido)
- **Component:** Controller + View = páginas dinámicas

---

## W

**WEB API**
- **ES:** API Web
- **Tipo:** REST API (en el curso)
- **Protocolo:** HTTP/HTTPS
- **Formato:** JSON

---

## X

**XML** (eXtensible Markup Language)
- **ES:** Lenguaje de Marcado Extensible
- **Uso:** Poco usado en curso (antes era común)
- **Contraste:** JSON es más moderno y compacto

---

## Y

**YML/YAML** (YAML Ain't Markup Language)
- **ES:** Lenguaje de Serialización de Datos
- **Uso:** GitHub Actions, Docker Compose, Kubernetes
- **Sintaxis:** Indentación basada en espacios

---

## Z

---

## 📚 Abreviaturas comunes

| Abrevia. | Significado |
|----------|-------------|
| API | Application Programming Interface |
| DB / BD | Database / Base de Datos |
| Auth | Autenticación / Autorización |
| JWT | JSON Web Token |
| SPA | Single Page Application |
| MPA | Multi-Page Application  |
| REST | Representational State Transfer |
| HTTP | HyperText Transfer Protocol |
| SQL | Structured Query Language |
| CRUD | Create, Read, Update, Delete |
| DTO | Data Transfer Object |
| ORM | Object-Relational Mapping |
| DI | Dependency Injection |
| CORS | Cross-Origin Resource Sharing |
| URL | Uniform Resource Locator |
| URI | Uniform Resource Identifier |
| JSON | JavaScript Object Notation |
| XML | eXtensible Markup Language |
| HTML | HyperText Markup Language |
| CSS | Cascading Style Sheets |
| JS | JavaScript |
| TS | TypeScript |
| C# | C Sharp |
| .NET | Plataforma de Microsoft |
| SP | Stored Procedure |
| PK | Primary Key |
| FK | Foreign Key |
| GUID | Globally Unique Identifier |
| HTTPS | HTTP Secure |
| TLS | Transport Layer Security |
| SSL | Secure Sockets Layer |

---

*Glosario del Curso SC701 — Referencia de términos técnicos en español e inglés*
