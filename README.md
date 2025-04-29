# Introducción

Aplicación web desarrollada como Trabajo de Aplicación Práctica (TAP) para obtener el título técnico intermedio en AIEP año 2025, por Johann Mora Mira (estudiante de tercer año de Ingeniería en Ejecución Informática).
Este sistema corresponde a un sistema de gestión para un taller mecánico ficticio especializado en Ford llamado "Taller El Óvalo", en referencia al clásico logo de la marca americana. 
Quise buscar un proyecto que me divirtiera y mezcle dos cosas que me apasionan, la informática y la mecánica. Esta ha sido una experiencia formativa y bastante divertida. 


## Descripción del Problema y Solución

El proyecto aborda la problemática de la gestión manual de inventarios en talleres pequeños, la cual tiene problemas relacionados a la inexactitud del stock, falta de trazabilidad y pérdida de tiempo, entre otros.

La solución implementada es esta aplicación web ("Taller El Óvalo Web App") que permite:

*   Gestionar trabajadores (añadir, listar, activar/desactivar).
*   Gestionar repuestos (añadir, listar, ver stock actual).
*   Registrar movimientos de inventario:
    *   Entradas: Incrementan el stock.
    *   Asignaciones: A trabajadores, con OT opcional, validando y disminuyendo stock.
    *   Mermas: Registran pérdidas, con motivo opcional, disminuyendo stock.
*   Buscar y filtrar el historial de todos los movimientos por diversos criterios (fechas, repuesto, trabajador, OT), funcionando como un sistema básico de reportes.
*   Presentar una interfaz de usuario clara, responsive para desktop y mobile y estilizada con estilos de Bootstrap, CSS personalizado, iconos CDN y formato de fecha/hora local (Chile).


## Tecnologías Utilizadas

*   **Backend:** Python 3.10+
*   **Framework Web:** Flask 3.x
*   **Base de Datos:** MySQL 8.0+
*   **ORM:** SQLAlchemy (con Flask-SQLAlchemy)
*   **Formularios:** Flask-WTF (WTForms)
*   **Servidor WSGI:** Gunicorn
*   **Frontend:** HTML5, CSS3, Jinja2
*   **Framework CSS:** Bootstrap 5.3
*   **Iconos:** Bootstrap Icons
*   **Tipografía:** Google Fonts (Sansation)
*   **Librerías Python Adicionales:** mysql-connector-python, python-dotenv, pytz
*   **Plataforma de Despliegue:** Railway.app

## Configuración y Ejecución Local

Paso a paso para ejecutar la aplicación de manera local:

1.  **Prerrequisitos:**
    *   Python 3.10 o superior instalado.
    *   `pip` instalado.
    *   Git instalado (para clonar).
    *   Servidor MySQL 8.0 o superior instalado y corriendo.

2.  **Abrir una terminal Bash y clonar el Repositorio**:
    "git clone https://github.com/TU_USUARIO_GITHUB/taller-el-ovalo-app.git"
    "cd taller-el-ovalo-app"
    

3.  **Ya en el directorio raíz, crear y Activar Entorno Virtual en una terminal Bash**:
    # Windows (Git Bash / WSL / Linux / macOS):
    "python -m venv venv"
    "source venv/bin/activate" #(en el caso de Linux/macOS/WSL)
    # o
    "source venv/Scripts/activate" (en el caso de usar Git Bash en Windows / CMD / PowerShell)


5.  **Instalar Dependencias**:
    "pip install -r requirements.txt"

6.  **Configurar Base de Datos MySQL:**
    *   Conéctate a tu servidor MySQL local (con MySQL Workbench o la línea de comandos).
    *   Crea una base de datos vacía para la aplicación:
        ```sql
        CREATE DATABASE taller_ford_db CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
        ```
        *(Puedes usar otro nombre si lo prefieres, pero deberás ajustarlo en el siguiente paso).*

7.  **Configurar Variables de Entorno:**
    *   Crea un archivo llamado ".env" en la raíz del proyecto ("taller-el-ovalo-app/.env").
    *   Añade el siguiente contenido, **reemplazando los valores entre `<...>`** con tus propios datos:

        ```dotenv
        # .env
        FLASK_APP=run.py
        FLASK_DEBUG=1 # 1 para desarrollo, 0 para producción
        SECRET_KEY='<UNA_CLAVE_SECRETA_MUY_LARGA_Y_ALEATORIA_AQUI>' # ¡Cámbiala!

        # Configuración de tu Base de Datos MySQL LOCAL
        DATABASE_URL='mysql+mysqlconnector://<tu_usuario_mysql>:<tu_contraseña_mysql>@localhost/taller_ford_db'
        # Ejemplo: DATABASE_URL='mysql+mysqlconnector://root:pass@localhost/taller_ford_db'
        ```

8.  **Crear las Tablas:**
    *   Flask creará las tablas automáticamente la primera vez que se ejecute gracias a `db.create_all()` en `app/__init__.py`.

9.  **Ejecutar la Aplicación:**
    "flask run"
    *   La aplicación estará disponible en tu navegador en `http://localhost:5000`.


## Despliegue en Railway

La aplicación está desplegada y accesible públicamente en:

*   **URL:** [https://taller-el-ovalo-app-production.up.railway.app/index]


## Autor

*   Johann Mora Mira
*   Trabajo de Aplicación Práctica - Ingeniería en Ejecución Informática Mención Desarrollo de Sistemas
*   Instituto Profesional AIEP - Sede Online
*   2025

---
