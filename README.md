## Descripción del proyecto
Aplicación web desarrollada con Django y MySQL para gestionar una biblioteca. Permite registrar libros y autores, consultar información, realizar búsquedas y visualizar estadísticas, aplicando los conceptos básicos de desarrollo web vistos en clase.


---


## Instrucciones de instalación

✅ Requisitos previos<br><br>
🧰 Software necesario
- Python 3.10 o superior
- MySQL Server 8.0 o superior
- Git
- Visual Studio Code (editor recomendado)
- Navegador web moderno

👤 Cuentas requeridas
- Cuenta de GitHub (gratuita): https://github.com
- Cuenta de PythonAnywhere (gratuita): https://www.pythonanywhere.com

📦 Parte 1: Configuración del entorno<br><br>
🔹 Paso 1.1: Verificar instalación de Python<br><br>
Abrir PowerShell como Administrador y ejecutar los siguientes comandos:
```text
python --version
Salida esperada: Python 3.10.x o superior

pip --version
```

🔹 Paso 1.2: Crear directorio del proyecto<br>
```text
mkdir C:\Proyectos\biblioteca_django
cd C:\Proyectos\biblioteca_django
```

🔹 Paso 1.3: Crear entorno virtual
```text
python -m venv venv

Activar el entorno virtual (Windows):

.\venv\Scripts\Activate
```

Nota:
Siempre trabaja con el entorno virtual activado.
Si cierras la terminal, deberás activarlo nuevamente con:
.\venv\Scripts\Activate

🔹 Paso 1.4: Instalar Django y dependencias

```text
# Actualizar pip:

python -m pip install --upgrade pip

# Instalar Django:

pip install Django==4.2

# Instalar conector MySQL:

pip install mysqlclient

# Instalar otras dependencias:

pip install pillow

# Crear archivo requirements.txt:

pip freeze > requirements.txt
```

🏗️ Parte 2: Creación del proyecto Django<br><br>
🔹 Paso 2.1: Crear proyecto Django
```text
django-admin startproject biblioteca_project .
```

```text
Verificar la estructura creada:
dir
```

🔹 Paso 2.2: Crear aplicación libros
```text
python manage.py startapp libros
```

🗄️ Configuración de la base de datos<br><br>
🔹 Crear base de datos en MySQL<br><br>
Abrir MySQL y ejecutar los siguientes comandos:<br>
```text
CREATE DATABASE biblioteca_django
CHARACTER SET utf8mb4
COLLATE utf8mb4_general_ci;

CREATE USER 'biblioteca_user'@'localhost' IDENTIFIED BY 'password';
GRANT ALL PRIVILEGES ON biblioteca_django.* TO 'biblioteca_user'@'localhost';
FLUSH PRIVILEGES;
```

🔹 Configurar conexión en Django
Configurar las credenciales de la base de datos en el archivo .env
```text
DB_NAME=biblioteca_django
DB_USER=biblioteca_user
DB_PASSWORD=password
DB_HOST=localhost
DB_PORT=3306
```
🔄 Migraciones de la base de datos
```text
🔹 Ejecutar migraciones
python manage.py makemigrations

python manage.py migrate
```

Estos comandos crean las tablas necesarias en la base de datos.

🔹 Crear superusuario (opcional pero recomendado)
```text
python manage.py createsuperuser
```
🔹 Ejecutar el servidor
```text
python manage.py runserver
```

Abrir el navegador en:
```text
http://127.0.0.1:8000/
```

## Tecnologías utilizadas
- Python 3.1x
- Django 4.2
- MySQL
- Bootstrap
- HTML, CSS, JavaScript
- Git/GitHub

---

## Estructura del proyecto

```text
biblioteca_django/
│
├── biblioteca_project/           # Configuración principal del proyecto
│   ├── __pycache__/
│   ├── __init__.py
│   ├── asgi.py
│   ├── settings.py               # Configuración general de Django
│   ├── urls.py                   # URLs principales
│   └── wsgi.py
│
├── libros/                       # Aplicación principal
│   ├── __pycache__/
│   ├── migrations/               # Migraciones de la base de datos
│   ├── __init__.py
│   ├── admin.py                  # Registro de modelos en el admin
│   ├── apps.py                   # Configuración de la app
│   ├── models.py                 # Modelos (Libros, Autores, etc.)
│   ├── tests.py                  # Pruebas
│   ├── urls.py                   # URLs de la app libros
│   └── views.py                  # Vistas y lógica del sistema
│
├── media/                        # Archivos subidos por usuarios
│
├── static/                       # Archivos estáticos
│   ├── css/
│   │   └── styles.css             # Estilos CSS
│   ├── images/                    # Imágenes del proyecto
│   └── js/                        # Archivos JavaScript
│
├── templates/                    # Templates HTML
│   ├── base/
│   │   └── base.html              # Template base (navbar, footer)
│   └── libros/
│       ├── inicio.html            # Página principal
│       ├── lista_libros.html      # Lista de libros
│       ├── detalle_libro.html     # Detalle de libro
│       ├── lista_autores.html     # Lista de autores
│       ├── detalle_autor.html     # Detalle de autor
│       ├── busqueda_avanzada.html # Búsqueda avanzada
│       └── estadisticas.html      # Estadísticas del sistema
│
├── .env                          # Variables de entorno
├── .gitignore                    # Archivos ignorados por Git
├── manage.py                     # Comando principal de Django
└── requirements.txt              # Dependencias del proyecto
```
---

## Autor

**Nombre:** Gabriel Alejandro Montaño Oquita<br>
**Grupo:** TIDS5-1<br>
**Carrera:** TSU en Desarrollo de Software Multiplataforma<br>
**Universidad:** Universidad Técnologica de Hermosillo<br>

---
