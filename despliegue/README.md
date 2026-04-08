# ☁️ Despliegue — Azure, CI/CD, GitHub Actions

📁 [Documentación](../README.md) / 📁 **Despliegue**

---

Cómo publicar los 3 proyectos en Azure usando GitHub Actions.

---

## 📚 Contenidos

- [Git Flow Workflow](gitflow-workflow.md) — Estrategia de ramas
- Configuración de Azure (App Service, SQL Database)
- GitHub Actions workflows (.yml)
- Secretos y variables de entorno
- Publicación de DB con DACPAC
- Monitoreo y logging
- Troubleshooting

---

## 🚀 Escenarios de deployment

| Proyecto | Target | Método | Config |
|----------|--------|--------|--------|
| API | Azure App Service | dotnet publish | Program.cs + appsettings |
| WEB | Azure App Service | dotnet publish | Program.cs + appsettings |
| React | Azure Static Web Apps | npm build | vite.config.ts |
| DB | Azure SQL | DACPAC | .sqlproj |

---

## 📋 Pasos generales

1. **Crear App Services en Azure** (API, WEB, React)
2. **Crear Azure SQL Database** 
3. **Configurar GitHub Secrets** (credenciales de Azure)
4. **Crear archivos `.yml`** en `.github/workflows/`
5. **Push a main** → GitHub Actions dispara workflows
6. **Verificar en Azure** → revisar logs

---

## 🔐 Secretos necesarios

- `AZURE_WEBAPP_PUBLISH_PROFILE` — API  
- `AZURE_WEBAPP_PUBLISH_PROFILE_WEB` — WEB
- `AZURE_WEBAPP_PUBLISH_PROFILE_REACT` — React
- `AZURE_SQL_CONNECTION_STRING` — Database

---

*Documentación del Curso SC701 — Despliegue y CI/CD*
