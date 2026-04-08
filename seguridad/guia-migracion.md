# 🔐 Guía de Migración: De sin seguridad → con seguridad

📁 [Documentación](../README.md) / 📁 [Seguridad](README.md)

---

> **Para quién es esta guía:** Estudiantes que ya tienen el código de la Semana 05 funcionando y quieren agregar autenticación.

Referencia completa disponible en: `/2026C01/CodigoBase/Semana 06-API y WEB con Seguridad`

---

## 📊 ¿Qué cambia?

```
SEMANA 05 (sin seguridad):
  API → Controllers sin [Authorize]
  WEB → Razor sin login
  
SEMANA 06 (con seguridad):
  API → Controllers con [Authorize(Roles = "1")]
  WEB → Razor Pages + Login/Logout
  API Seguridad → genera JWT
```

---

## 🔧 Cambios principales

### En el API de Vehículos

1. Instalar paquetes NuGet (JWT Bearer + Autorización)
2. Crear modelo `Token.cs`
3. Agregar sección "Token" en `appsettings.json`
4. Modificar `Program.cs` (agregar JWT + middleware)
5. Proteger Controllers con `[Authorize(Roles = "1")]`

### En la WEB

1. Instalar paquetes NuGet (autorización)
2. Crear modelos de seguridad (`Login.cs`)
3. Crear archivos `.cs` en `Reglas/Autenticacion.cs`
4. Crear páginas Razor (`Pages/Cuenta/Login.cshtml` y otros)
5. Modificar `Program.cs` (agregar cookie auth)
6. Proteger páginas con `[Authorize]`

---

*Para pasos detallados, consulta `guia-migracion-seguridad.md` en el archivo original adjunto.*
