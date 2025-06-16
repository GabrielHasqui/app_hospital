# 🏥 Sistema de Gestión Hospitalaria

Sistema de gestión hospitalaria desarrollado con Django, PostgreSQL y Tailwind CSS.

## 📋 Requisitos del Sistema

- Python 3.8+
- Node.js 16+ y npm
- PostgreSQL 12+
- Git

## 🚀 Instalación y Configuración

### 1. Clonar el Repositorio

```bash
git clone [URL_DEL_REPOSITORIO]
cd app_hospital
```

### 2. Crear y Activar Entorno Virtual

**En Windows:**

```cmd
python -m venv venv
venv\Scripts\activate
```

**En Linux/macOS:**

```bash
python3 -m venv venv
source venv/bin/activate
```

### 3. Instalar Dependencias de Python

```bash
pip install -r requirements.txt
```

### 4. Configurar Base de Datos PostgreSQL

1. **Instalar PostgreSQL** si no lo tienes instalado
2. **Crear la base de datos:**

```sql
-- Conectar a PostgreSQL como superusuario
psql -U postgres

-- Crear la base de datos
CREATE DATABASE medicos;

-- Crear usuario (opcional, puedes usar postgres)
CREATE USER tu_usuario WITH PASSWORD 'tu_contraseña';
GRANT ALL PRIVILEGES ON DATABASE medicos TO tu_usuario;
```

### 5. Configurar Variables de Entorno

Crear un archivo `.env` en la raíz del proyecto con el siguiente contenido:

```env
# Configuración de Django
SECRET_KEY=tu-clave-secreta-muy-segura-aqui
DEBUG=True

# Configuración de Base de Datos
DB_ENGINE=django.db.backends.postgresql
DB_NAME=medicos
DB_USER=postgres
DB_PASSWORD=123
DB_HOST=localhost
DB_PORT=5432
DB_CONN_MAX_AGE=0
DB_CONN_HEALTH_CHECKS=False
```

> **⚠️ Importante:** Cambia los valores por los de tu configuración real, especialmente la `SECRET_KEY` y las credenciales de la base de datos.

### 6. Configurar Node.js y Tailwind CSS

1. **Navegar al directorio de Tailwind:**

```bash
cd theme/static_src
```

2. **Instalar dependencias de Node.js:**

```bash
npm install
```

3. **Volver al directorio raíz:**

```bash
cd ../..
```

### 7. Configurar Django

1. **Realizar migraciones:**

```bash
python manage.py makemigrations
python manage.py migrate
```

2. **Crear superusuario:**

```bash
python manage.py createsuperuser
```

3. **Recopilar archivos estáticos:**

```bash
python manage.py collectstatic
```

### 8. Compilar CSS con Tailwind

**En una terminal separada, ejecutar:**

```bash
python manage.py tailwind start
```

Este comando iniciará el modo de desarrollo de Tailwind que recompilará automáticamente los estilos.

## 🏃‍♂️ Ejecutar el Proyecto

### Desarrollo

1. **Terminal 1 - Servidor Django:**

```bash
python manage.py runserver
```

2. **Terminal 2 - Tailwind (modo desarrollo):**

```bash
python manage.py tailwind start
```

El proyecto estará disponible en: `http://127.0.0.1:8000/`

### Producción

Para producción, compila los estilos de Tailwind:

```bash
python manage.py tailwind build
```

## 📁 Estructura del Proyecto

```
app_hospital/
├── applications/           # Aplicaciones Django
│   ├── core/              # Aplicación principal
│   ├── doctor/            # Gestión de doctores
│   └── security/          # Autenticación y seguridad
├── proy_clinico/          # Configuración del proyecto
├── static/                # Archivos estáticos
├── templates/             # Plantillas HTML
├── theme/                 # Configuración de Tailwind CSS
├── manage.py              # Script de gestión Django
├── requirements.txt       # Dependencias Python
└── .env                   # Variables de entorno (crear)
```

## 🛠️ Comandos Útiles

### Django

```bash
# Crear migraciones
python manage.py makemigrations

# Aplicar migraciones
python manage.py migrate

# Crear superusuario
python manage.py createsuperuser

# Shell interactivo
python manage.py shell

# Recopilar archivos estáticos
python manage.py collectstatic
```

### Tailwind CSS

```bash
# Modo desarrollo (watch)
python manage.py tailwind start

# Compilar para producción
python manage.py tailwind build

# Instalar dependencias de Tailwind
python manage.py tailwind install
```

## 🔧 Configuración Adicional

### Configurar Node.js Path (Windows)

Si tienes problemas con Node.js en Windows, asegúrate de que la ruta en `settings.py` sea correcta:

```python
NPM_BIN_PATH = r"C:\Program Files\nodejs\npm.cmd"
```

### Variables de Entorno Disponibles

| Variable      | Descripción             | Valor por Defecto |
| ------------- | ----------------------- | ----------------- |
| `SECRET_KEY`  | Clave secreta de Django | (requerido)       |
| `DEBUG`       | Modo debug              | `False`           |
| `DB_NAME`     | Nombre de la BD         | `medicos`         |
| `DB_USER`     | Usuario de PostgreSQL   | `postgres`        |
| `DB_PASSWORD` | Contraseña de BD        | `123`             |
| `DB_HOST`     | Host de la BD           | `localhost`       |
| `DB_PORT`     | Puerto de PostgreSQL    | `5432`            |

## 🧪 Pruebas

Para ejecutar las pruebas:

```bash
python manage.py test
```

## 📝 Notas Importantes

1. **Seguridad:** Nunca subas el archivo `.env` al repositorio
2. **Producción:** Cambia `DEBUG=False` en producción
3. **Secret Key:** Genera una nueva clave secreta para producción
4. **Base de Datos:** Configura backups regulares de PostgreSQL
5. **Tailwind:** En producción, usa `tailwind build` en lugar de `tailwind start`

## 🤝 Contribuir

1. Fork el proyecto
2. Crea una rama feature (`git checkout -b feature/nueva-funcionalidad`)
3. Commit tus cambios (`git commit -am 'Agregar nueva funcionalidad'`)
4. Push a la rama (`git push origin feature/nueva-funcionalidad`)
5. Abre un Pull Request

## 📄 Licencia

[Especificar licencia aquí]

## 📞 Soporte

Para soporte técnico, contactar a [tu-email@ejemplo.com]

---

⚡ **¡Listo para usar!** El sistema debería estar funcionando correctamente siguiendo estos pasos.
