# 🌐 Frontend Web — Razor Pages

Arquitectura, patrones y convenciones de **Vehiculos.WEB** en ASP.NET Core Razor Pages.

---

## 📚 Contenidos

- Estructura de Razor Pages (.cshtml + .cs)
- Patrón PageModel
- HttpClient con Bearer token
- Binding de propiedades
- Validación client-side
- Integración con API

---

## 📐 Estructura típica

```
Pages/
├── Vehiculos/
│   ├── Index.cshtml       (lista)
│   ├── Index.cshtml.cs    (code-behind)
│   ├── Detalle.cshtml     (GET un vehículo)
│   ├── Detalle.cshtml.cs
│   ├── Agregar.cshtml     (POST nuevo)
│   ├── Agregar.cshtml.cs
│   ├── Editar.cshtml      (PUT)
│   ├── Editar.cshtml.cs
│   └── Eliminar.cshtml    (DELETE)
└── Cuenta/
    ├── Login.cshtml
    ├── Login.cshtml.cs
    ├── Logout.cshtml.cs
    └── Registro.cshtml
```

---

## 🔄 Patrón: PageModel

```csharp
[Authorize]  // ← Requiere autenticación
public class IndexModel : PageModel
{
    [BindProperty]
    public List<VehiculoResponse> vehiculos { get; set; }

    public async Task OnGetAsync()  // GET
    {
        // Obtener datos
    }

    public async Task<IActionResult> OnPostAsync()  // POST
    {
        // Guardar
        return RedirectToPage("Index");
    }
}
```

---

## 🔑 Convenciones

- Métodos: `OnGet`, `OnPost`, `OnPut`, `OnDelete`
- Propiedades públicas: Binding automático
- `[BindProperty]`: Vincula al modelo
- `[FromRoute]`: Parámetro en URL
- Redirección: `RedirectToPage()` o `Redirect()`

---

## 📋 Checklist: Tu WEB es válida si …

- [ ] Todas las pages que listan/editan tienen `[Authorize]`
- [ ] Usas `ObtenerClienteConToken()` para llamadas al API (tiene Bearer)
- [ ] `[BindProperty]` en todos los modelos de forma
- [ ] Validaciones con DataAnnotations (`[Required]`, `[EmailAddress]`, etc.)
- [ ] CORS configurado en el API para permitir el origin del WEB

---

*Documentación del Curso SC701 — Frontend Web (Razor Pages)*
