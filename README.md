# Taller El Óvalo App - TAP AIEP

Aplicación web desarrollada como Trabajo de Aplicación Práctica (TAP) para AIEP [Sede Online] [2025] por Johann Mora Mira, estudiante de Tercer Año de Ingeniería en Ejecución Informática. 
El desarrollo de este trabajo tiene como fin la obtención del título técnico intermedio mientras se cursa la carrera profesional completa.
Esta aplicación es un sistema de gestión de inventario de insumos y respuestos para un taller mecánico ficticio especializado en la marca americana Ford, llamado "Taller El Óvalo".
Quise mezclar dos mundos que me apasionan: la informática y la mecánica.
Espero les guste este trabajo tanto como me divertí desarrollándolo, diseñando el logo, interfaz y resolviendo los desafíos que salían en el camino. 

Agradecimientos especiales a mi esposa Samanta quien me cebó mates durante todo Abril 2025 mientras trabajaba en este proyecto después de mi jornada laboral. 


## Descripción del Problema y Solución

El proyecto aborda la problemática de la gestión manual de inventarios en talleres pequeños, la cual tiene problemas relacionados a la inexactitud del stock, falta de trazabilidad y pérdida de tiempo en operaciones manuales.

La solución implementada es esta aplicación web ("Taller El Óvalo App") que permite:

*   Gestionar trabajadores (añadir, listar, activar/desactivar).
*   Gestionar repuestos (añadir, listar, ver stock actual).
*   Registrar movimientos de inventario:
    *   **Entradas:** Incrementan el stock.
    *   **Asignaciones:** A trabajadores, con OT opcional, validando y disminuyendo stock.
    *   **Mermas:** Registran pérdidas, con motivo opcional, disminuyendo stock.
*   Buscar y filtrar el historial de todos los movimientos por diversos criterios (fechas, repuesto, trabajador, OT), funcionando como un sistema básico de reportes.
*   Presentar una interfaz de usuario clara, responsive y estilizada con Bootstrap, iconos y formato de fecha/hora local (Chile).



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

Sigue estos pasos para ejecutar la aplicación en tu máquina local:

1.  **Prerrequisitos:**
    *   Python 3.10 o superior instalado.
    *   Git instalado.
    *   Servidor MySQL 8.0 o superior instalado y corriendo.

2.  **Clonar el Repositorio:**
    ```bash
    git clone https://github.com/TU_USUARIO_GITHUB/taller-el-ovalo-app.git
    cd taller-el-ovalo-app
    ```

3.  **Crear y Activar Entorno Virtual:**
    ```bash
    # Windows (Git Bash / WSL / Linux / macOS)
    python -m venv venv
    source venv/bin/activate # Linux/macOS/WSL
    # o source venv/Scripts/activate # Git Bash en Windows / CMD / PowerShell

    ```

4.  **Instalar Dependencias:**
    ```bash
    pip install -r requirements.txt
    ```

5.  **Configurar Base de Datos MySQL:**
    *   Conéctate a tu servidor MySQL local (con MySQL Workbench o la línea de comandos).
    *   Crea una base de datos vacía para la aplicación:
        ```sql
        CREATE DATABASE taller_ford_db CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
        ```

6.  **Configurar Variables de Entorno:**
    *   Crea un archivo llamado `.env` en la raíz del proyecto (`taller-el-ovalo-app/.env`).
    *   Añade el siguiente contenido, **reemplazando los valores entre `<...>`** con tu propio usuario y contraseña MySQL:

        ```dotenv
        # .env
        FLASK_APP=run.py
        FLASK_DEBUG=1 # 1 para desarrollo, 0 para producción
        SECRET_KEY='<UNA_CLAVE_SECRETA_MUY_LARGA_Y_ALEATORIA_AQUI>' # ¡Cámbiala!

        # Configuración de tu Base de Datos MySQL LOCAL
        DATABASE_URL='mysql+mysqlconnector://<tu_usuario_mysql>:<tu_contraseña_mysql>@localhost/taller_ford_db'
        # Ejemplo: DATABASE_URL='mysql+mysqlconnector://root:pass@localhost/taller_ford_db'
        ```

7.  **Crear las Tablas:**
    *   Flask creará las tablas automáticamente la primera vez que se ejecute gracias a `db.create_all()` en `app/__init__.py`.

8.  **Ejecutar la Aplicación:**
    ```bash
    flask run
    ```
    *   La aplicación estará disponible en el navegador en localhost, URL: `http://localhost:5000`.



## Despliegue en Railway

La aplicación está desplegada y accesible públicamente en:

*   **URL:** **[https://taller-el-ovalo-app-production.up.railway.app/index]**



## Autor

*   **[Johann Mora Mira]**
*   Trabajo de Aplicación Práctica - [Ineniería en Ejecución Informática Mención Desarrollo de Sistemas]
*   Instituto Profesional AIEP - [Sede Online]
*   [2025]

---
