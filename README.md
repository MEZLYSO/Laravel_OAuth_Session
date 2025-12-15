# Aplicación de Autenticación OAuth con Laravel

## Descripción General

Esta es una aplicación web desarrollada con el framework Laravel que implementa un sistema de autenticación completo para usuarios. La aplicación soporta dos métodos de autenticación:

- **Autenticación tradicional**: Registro y login mediante email y contraseña.
- **Autenticación OAuth**: Login mediante Google OAuth 2.0.

La aplicación utiliza:
- **Laravel Breeze**: Para la interfaz de usuario de autenticación (login, registro, recuperación de contraseña, verificación de email).
- **Laravel Socialite**: Para la integración con proveedores OAuth como Google.
- **Tailwind CSS**: Para el diseño y estilos de la interfaz.
- **Pest**: Para las pruebas automatizadas.

Características principales:
- Registro de usuarios con verificación de email.
- Login y logout seguros.
- Recuperación de contraseña.
- Gestión de perfil de usuario.
- Dashboard protegido para usuarios autenticados.
- Integración con Google para login social.

## Requisitos Previos

Antes de ejecutar la aplicación, asegúrate de tener instalados los siguientes componentes:

- **PHP 8.2 o superior**
- **Composer** (gestor de dependencias de PHP)
- **Node.js y npm** (para la gestión de assets frontend)
- **Base de datos** compatible con Laravel (MySQL, PostgreSQL, SQLite, etc.)

## Instalación y Configuración

Sigue estos pasos para configurar y ejecutar la aplicación:

### 1. Clonar el Repositorio

```bash
git clone <url-del-repositorio>
cd Laravel_OAuth_session/authApp
```

### 2. Instalar Dependencias

Instala las dependencias de PHP con Composer:

```bash
composer install
```

Instala las dependencias de Node.js:

```bash
npm install
```

### 3. Configurar el Entorno

Copia el archivo de ejemplo de configuración:

```bash
cp .env.example .env
```

Edita el archivo `.env` y configura las siguientes variables:

- **Base de datos**:
  ```
  DB_CONNECTION=mysql
  DB_HOST=127.0.0.1
  DB_PORT=3306
  DB_DATABASE=laravel_oauth
  DB_USERNAME=tu_usuario
  DB_PASSWORD=tu_contraseña
  ```

- **Google OAuth** (obtén las credenciales desde Google Cloud Console):
  ```
  GOOGLE_CLIENTID=tu_google_client_id
  GOOGLE_CLIENTSECRET=tu_google_client_secret
  ```

- Otras configuraciones necesarias (APP_NAME, APP_URL, etc.).

### 4. Ejecutar Migraciones

Crea las tablas en la base de datos:

```bash
php artisan migrate
```

### 5. Construir Assets

Compila los archivos CSS y JS:

```bash
npm run build
```

## Uso

### Ejecutar la Aplicación

Para ejecutar:

```bash
php artisan serve -host domain.com --port=80
```

### Acceder a la Aplicación

1. Abre tu navegador y ve a `http://localhost:8000`
2. En la página de inicio, puedes:
   - Registrarte con email y contraseña
   - Iniciar sesión con credenciales existentes
   - Usar "Login con Google" para autenticación OAuth

### Rutas Principales

- `/`: Página de bienvenida
- `/login`: Página de login
- `/register`: Página de registro
- `/dashboard`: Dashboard (requiere autenticación)
- `/profile`: Gestión de perfil (requiere autenticación)
- `/google-auth/redirect`: Redirección a Google OAuth
- `/google-auth/callback`: Callback de Google OAuth

## Estructura del Proyecto

```
authApp/
├── app/                 # Código de la aplicación
├── bootstrap/           # Archivos de arranque
├── config/              # Configuraciones
├── database/            # Migraciones, seeders, factories
├── public/              # Archivos públicos
├── resources/           # Vistas, CSS, JS
├── routes/              # Definición de rutas
├── storage/             # Archivos temporales
├── tests/               # Pruebas
└── vendor/              # Dependencias de Composer
```
