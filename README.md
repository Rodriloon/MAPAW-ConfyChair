# Comfy Chair - Sistema de Gestión de Conferencias Académicas

Sistema integral para la gestión de conferencias académicas que permite la administración de artículos, revisiones, asignaciones y selección de trabajos.

## 📋 Descripción

Comfy Chair es una plataforma completa que facilita la organización y gestión de conferencias académicas, ofreciendo herramientas para:

- Gestión de conferencias y sesiones
- Envío y administración de artículos
- Sistema de revisión por pares
- Asignación de revisores
- Sistema de bidding para revisores
- Métodos de selección de artículos (porcentaje y mejora por umbral)
- Estadísticas y análisis de artículos
- Control de usuarios y autenticación

## 🏗️ Arquitectura del Proyecto

El proyecto está dividido en dos aplicaciones principales:

### Frontend - `comfy-chair-2025`
- **Framework**: React 18+ con TypeScript
- **Routing**: TanStack Router (file-based routing)
- **UI Components**: shadcn/ui + Radix UI
- **Estilos**: Tailwind CSS
- **Build Tool**: Vite
- **Estado**: React Context API (AuthContext)

### Backend - `comfy-chair-api-2025`
- **Framework**: Django 5.x + Django REST Framework
- **Base de Datos**: SQLite (desarrollo)
- **Autenticación**: Token-based authentication
- **Arquitectura**: API REST

## 📁 Estructura del Proyecto

```
MAPAW/
├── comfy-chair-2025/          # Aplicación Frontend
│   ├── src/
│   │   ├── components/        # Componentes React reutilizables
│   │   │   ├── article/       # Componentes de artículos
│   │   │   ├── bidding/       # Sistema de ofertas
│   │   │   ├── conference/    # Gestión de conferencias
│   │   │   ├── reviewer/      # Gestión de revisores
│   │   │   ├── Reviews/       # Sistema de revisiones
│   │   │   └── ui/            # Componentes UI de shadcn
│   │   ├── contexts/          # Context API (AuthContext)
│   │   ├── routes/            # Rutas de TanStack Router
│   │   ├── services/          # Servicios API
│   │   └── utils/             # Utilidades y hooks
│   └── public/                # Archivos estáticos
│
├── comfy-chair-api-2025/      # Aplicación Backend
│   ├── article/               # App de artículos
│   ├── conference/            # App de conferencias
│   ├── conference_session/    # App de sesiones
│   ├── user/                  # App de usuarios
│   ├── media/                 # Archivos subidos
│   └── comfy_chair/           # Configuración del proyecto
│
├── .git-backup-comfy-chair-2025/      # Backup del repositorio frontend
└── .git-backup-comfy-chair-api-2025/  # Backup del repositorio backend
```

## 🚀 Instalación y Configuración

### Prerequisitos

- Node.js 18+ y npm
- Python 3.10+
- Git

### Frontend Setup

```bash
cd comfy-chair-2025

# Instalar dependencias
npm install

# Ejecutar en modo desarrollo
npm run dev

# Construir para producción
npm run build
```

El frontend estará disponible en `http://localhost:5173`

### Backend Setup

```bash
cd comfy-chair-api-2025

# Crear entorno virtual (opcional pero recomendado)
python -m venv venv
.\venv\Scripts\Activate.ps1  # Windows PowerShell
# source venv/bin/activate    # Linux/Mac

# Instalar dependencias
pip install -r requirements.txt

# Ejecutar migraciones
python manage.py migrate

# Crear superusuario (opcional)
python manage.py createsuperuser

# Ejecutar servidor de desarrollo
python manage.py runserver
```

El backend estará disponible en `http://localhost:8000`

## ✨ Características Principales

### Gestión de Conferencias
- Creación y edición de conferencias
- Configuración de sesiones con diferentes métodos de selección
- Control de deadlines y fases

### Sistema de Artículos
- Envío de artículos (Regular / Poster)
- Estados de artículos: recepción, bidding, asignación, revisión, selección, aceptado, rechazado
- Visualización de estadísticas por tipo y estado

### Sistema de Revisión
- Asignación de revisores a artículos
- Proceso de bidding para que los revisores elijan artículos
- Sistema de revisiones con calificaciones

### Métodos de Selección
- **Porcentaje**: Selección basada en un porcentaje de los mejores artículos
- **Umbral de Mejora**: Selección basada en mejora mínima respecto al promedio

### Estadísticas y Análisis
- Gráficos de artículos aceptados vs rechazados
- Distribución por tipo (Regular vs Poster)
- Análisis por sesión y método de selección
- Indicadores visuales de capacidad y aprobación

## 🔐 Autenticación

El sistema implementa autenticación basada en tokens:

- Login/Registro de usuarios
- Rutas protegidas con `AuthContext`
- Middleware de autenticación en el backend

## 📊 Tecnologías Utilizadas

### Frontend
- React 18
- TypeScript
- TanStack Router
- shadcn/ui
- Radix UI
- Tailwind CSS
- Lucide React (iconos)
- Vite

### Backend
- Django 5.x
- Django REST Framework
- Python 3.10+
- SQLite

## 🔄 Restauración de Repositorios Git

Este repositorio contiene backups de los repositorios Git originales. Para restaurarlos:

### Frontend
```bash
cd comfy-chair-2025
Copy-Item -Path "../.git-backup-comfy-chair-2025" -Destination ".git" -Recurse
```

### Backend
```bash
cd comfy-chair-api-2025
Copy-Item -Path "../.git-backup-comfy-chair-api-2025" -Destination ".git" -Recurse
```

## 👥 Desarrollo

Este proyecto fue desarrollado como parte del curso MAPAW (Metodologías Ágiles de Programación y Aplicaciones Web) de la Universidad Nacional de La Plata.

### Grupos de Trabajo
- Frontend: Grupo 3
- Backend: Grupo 3

## 📝 Notas

- El proyecto utiliza SQLite en desarrollo. Para producción, considerar migrar a PostgreSQL o MySQL
- Los archivos de medios se almacenan en `comfy-chair-api-2025/media/`
- La configuración de CORS está habilitada para desarrollo local

## 🛠️ Scripts Disponibles

### Frontend
- `npm run dev` - Servidor de desarrollo
- `npm run build` - Build de producción
- `npm run preview` - Preview del build

### Backend
- `python manage.py runserver` - Servidor de desarrollo
- `python manage.py migrate` - Ejecutar migraciones
- `python manage.py test` - Ejecutar tests

## 📄 Licencia

Este proyecto es parte de un trabajo académico.

---

**Desarrollado con ❤️ para MAPAW - UNLP**
