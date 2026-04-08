# 🗄️ Base de Datos — SQL Server y Dapper

Estructura de BD, stored procedures y query patterns.

---

## 📚 Contenidos

- Tablas y relaciones (Vehiculo, Marca, Modelo)
- Stored Procedures (CREATE, READ, UPDATE, DELETE)
- Dapper patterns (QueryAsync, ExecuteScalarAsync)
- Índices y optimización
- Scripts de inicialización

---

## 📊 Esquema principal

```
Marca
  ├─ Id (PK)
  └─ Nombre

Modelo
  ├─ Id (PK)
  └─ IdMarca (FK) → Marca
  └─ Nombre

Vehiculo
  ├─ Id (PK)
  ├─ IdModelo (FK) → Modelo
  ├─ Placa
  ├─ Color
  ├─ Año
  ├─ Precio
  └─ CorreoPropietario
```

---

## 🔑 Patrón Dapper

```csharp
// Query (SELECT)
var vehiculos = await connection.QueryAsync<Vehiculo>(
    "ObtenerVehiculos");  // Stored Procedure name only

// Execute (INSERT/UPDATE/DELETE)
var newId = await connection.ExecuteScalarAsync<Guid>(
    "AgregarVehiculo", 
    new { Id = Guid.NewGuid(), Placa = "ABC-123", ... },
    commandType: CommandType.StoredProcedure);
```

---

*Documentación del Curso SC701 — Base de datos*
