# API de gestión de entrenadores

Una API RESTful para gestionar entrenadores de gimnasio y sus actividades.

## Características

- Operaciones CRUD completas para entrenadores.
- Punto final para enumerar actividades por entrenador
- Validación de datos
- Manejo de errores
- Documentación API con Swagger
## Instalación

```bash
# Instalar dependencias
instalación npm

# Iniciar el servidor
inicio de npm

# Iniciar el servidor con recarga automática (desarrollo)
npm ejecutar desarrollador
```

## Puntos finales API

Ruta base: `/entrenadores`

| Método | Punto final | Descripción |
|--------|----------|-------------|
| OBTENER | /entrenadores | Listar todos los entrenadores |
| OBTENER | /entrenadores/{id} | Consigue un entrenador específico |
| PUBLICAR | /entrenadores | Crear un nuevo entrenador |
| PONER | /entrenadores/{id} | Actualizar un entrenador |
| BORRAR | /entrenadores/{id} | Eliminar un entrenador |
| OBTENER | /entrenadores/{id}/actividades | Lista de actividades para un formador |

## 
Modelo de entrenador

```json
{
  "id": "string",
  "nombre": "string",
  "especialidad": "string",
  "horarios": ["lunes 8am", "miércoles 10am"],
  "certificaciones": ["string"]
}
```

## API Documentacion
Documentación

La documentación de Swagger está disponible en `/api-docs` cuando el servidor se está ejecutando.

## Solicitudes de muestra

### Consigue todos los entrenadores

```bash
curl -X OBTENER http://localhost:3000/trainers
```

### Consigue un entrenador específico

```bash
curl -X OBTENER http://localhost:3000/trainers/1
```

### Crear un nuevo entrenador

```bash
curl -X POST http://localhost:3000/entrenadores \
  -H "Tipo de contenido: aplicación/json" \
  -d '{
    "nombre": "Ana López",
    "especialidad": "Pilates",
    "horarios": ["martes 11am", "jueves 11am"],
    "certificaciones": ["Alianza Método Pilates", "BASI Pilates"]
  }'
```

### Actualizar un entrenador

```bash
curl -X PUT http://localhost:3000/trainers/1 \
  -H "Tipo de contenido: aplicación/json" \
  -d '{
    "nombre": "Juan Pérez",
    "especialidad": "CrossFit",
    "horarios": ["lunes 8am", "miércoles 10am", "viernes 8am"],
    "certificaciones": ["CrossFit Nivel 1", "CrossFit Nivel 2", "NASM CPT"]
  }'
```

### Eliminar un entrenador

```bash
curl -X BORRAR http://localhost:3000/trainers/1
```

### Obtener actividades para un entrenador

```bash
curl -X OBTENER http://localhost:3000/trainers/1/activities
```
