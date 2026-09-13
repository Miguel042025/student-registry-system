# Sistema de Registro de Estudiantes

Un sistema completo de registro de estudiantes con API REST local y interfaz gráfica en PySide6.

## Características

- ✅ API REST local con Flask
- ✅ Base de datos SQLite3
- ✅ Interfaz gráfica con PySide6
- ✅ Registro de estudiantes (nombre y edad)
- ✅ Búsqueda de estudiantes registrados
- ✅ CRUD completo (Crear, Leer, Actualizar, Eliminar)

## Requisitos

- Python 3.8+
- pip

## Instalación

1. Clonar el repositorio:
```bash
git clone https://github.com/Miguel042025/student-registry-system.git
cd student-registry-system
```

2. Crear un entorno virtual:
```bash
python -m venv venv
source venv/bin/activate  # En Windows: venv\Scripts\activate
```

3. Instalar dependencias:
```bash
pip install -r requirements.txt
```

## Uso

### 1. Iniciar la API

```bash
python api/app.py
```

La API estará disponible en: `http://localhost:5000`

### 2. Ejecutar la GUI

En otra terminal:
```bash
python gui/main.py
```

## Estructura del Proyecto

```
student-registry-system/
├── api/
│   ├── app.py              # Aplicación Flask (API REST)
│   ├── database.py         # Gestión de base de datos SQLite3
│   └── models.py           # Modelos de datos
├── gui/
│   ├── main.py             # Aplicación PySide6
│   └── ui/
│       └── main_window.py   # Interfaz principal
├── database/
│   └── estudiantes.db      # Base de datos SQLite3
├── requirements.txt        # Dependencias del proyecto
└── README.md              # Este archivo
```

## Endpoints de la API

### Obtener todos los estudiantes
```
GET /api/estudiantes
```

### Obtener estudiante por ID
```
GET /api/estudiantes/<id>
```

### Crear estudiante
```
POST /api/estudiantes
Content-Type: application/json

{
  "nombre": "Juan Pérez",
  "edad": 20
}
```

### Actualizar estudiante
```
PUT /api/estudiantes/<id>
Content-Type: application/json

{
  "nombre": "Juan Pérez",
  "edad": 21
}
```

### Eliminar estudiante
```
DELETE /api/estudiantes/<id>
```

### Buscar estudiante por nombre
```
GET /api/estudiantes/buscar?nombre=Juan
```

## Ejemplos de uso con cURL

```bash
# Crear estudiante
curl -X POST http://localhost:5000/api/estudiantes \
  -H "Content-Type: application/json" \
  -d '{"nombre":"María García","edad":22}'

# Obtener todos
curl http://localhost:5000/api/estudiantes

# Buscar por nombre
curl "http://localhost:5000/api/estudiantes/buscar?nombre=María"

# Actualizar
curl -X PUT http://localhost:5000/api/estudiantes/1 \
  -H "Content-Type: application/json" \
  -d '{"nombre":"María García","edad":23}'

# Eliminar
curl -X DELETE http://localhost:5000/api/estudiantes/1
```

## Autor

Miguel042025

## Licencia

MIT
