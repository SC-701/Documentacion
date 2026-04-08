# 📦 Publicar paquetes NuGet en GitHub Packages

> **Para quién es esta guía:** Quién mantiene o modifica el proyecto `Autorizacion.*` y necesita publicar una nueva versión.

---

## 🗺️ El proceso de un vistazo

```
1. Configurar metadatos en .csproj
2. Crear Personal Access Token (PAT) en GitHub  
3. Registrar feed en dotnet CLI
4. dotnet pack → genera .nupkg
5. dotnet nuget push → sube a GitHub Packages
```

---

## 🔑 Pasos principales

### Paso 1: Configurar .csproj

Agregar metadatos de paquete:

```xml
<PropertyGroup>
  <TargetFramework>net8.0</TargetFramework>
  
  <!-- Metadatos NuGet -->
  <PackageId>Autorizacion.Middleware</PackageId>
  <Version>2.0.6</Version>
  <Authors>Drojascode</Authors>
  <Company>SC701</Company>
  <Description>Middleware AutorizacionClaims() para ASP.NET Core</Description>
  <RepositoryUrl>https://github.com/Drojascode/SC701</RepositoryUrl>
  <GeneratePackageOnBuild>false</GeneratePackageOnBuild>
</PropertyGroup>
```

### Paso 2: Crear PAT en GitHub

1. GitHub → Settings → Developer settings → Personal access tokens
2. Generate token → scope: `write:packages`

### Paso 3: Registrar feed

```bash
dotnet nuget add source https://nuget.pkg.github.com/Drojascode/index.json `
  --name "GitHub-SC701" `
  --username TU_USUARIO `
  --password TU_TOKEN `
  --store-password-in-clear-text
```

### Paso 4: Empaquetar

```bash
dotnet pack -c Release
```

### Paso 5: Publicar

```bash
dotnet nuget push "bin/Release/Autorizacion.Middleware.2.0.6.nupkg" `
  --api-key TU_TOKEN `
  --source "https://nuget.pkg.github.com/Drojascode/index.json"
```

---

## ⚠️ Importante

- **Orden de publicación:** Abstracciones → DA → Flujo → Middleware
- **No se puede sobrescribir:** Si ya publicaste v2.0.6, incrementa a v2.0.7 antes de volver a publicar
- **Usar GitHub Actions:** Automatiza el proceso con workflows YML

---

*Para detalles completos, consulta `guia-publicar-paquetes.md` en los archivos adjuntos.*
