# ClassCheck

ClassCheck es un sistema web académico desarrollado para apoyar la organización de información relacionada con las clases y el seguimiento de los estudiantes. Su objetivo es facilitar el trabajo de estudiantes, docentes y administradores mediante herramientas accesibles desde un mismo lugar.

> **Estado del proyecto:** es una versión inicial. Algunas funciones, especialmente los flujos completos para registrar asistencia y calificaciones, todavía requieren desarrollo y pruebas. No está preparado para utilizarse en producción con datos personales reales.

## ¿Para qué sirve?

ClassCheck busca ayudar a organizar tareas académicas como la gestión de usuarios, carreras, unidades didácticas, horarios y plazos. También contempla distintos tipos de cuenta, de modo que cada persona acceda a las opciones correspondientes a su rol.

## Importancia

Mantener la información académica ordenada puede reducir tareas manuales y facilitar la consulta y el seguimiento del avance de los estudiantes. ClassCheck propone reunir parte de esa gestión en un sistema web, con permisos diferenciados para estudiantes, docentes y administradores.

## Roles del sistema

- **Administrador:** puede gestionar usuarios, carreras, unidades didácticas, horarios, plazos y solicitudes, además de consultar la auditoría.
- **Docente:** puede acceder a su panel y realizar acciones disponibles para su cuenta. Las cuentas docentes nuevas pueden quedar pendientes de aprobación.
- **Estudiante:** puede registrarse y acceder a las opciones habilitadas para su rol.

Los permisos se validan en el servidor según el rol asociado a la cuenta.

## Funcionalidades contempladas

- Inicio de sesión y control de acceso por rol.
- Registro de estudiantes y solicitudes de cuentas docentes.
- Creación inicial del primer administrador.
- Paneles de acceso según el tipo de usuario.
- Gestión básica de usuarios, carreras, unidades didácticas y horarios.
- Administración de plazos y solicitudes de reapertura.
- Registro de eventos de auditoría.
- Base de datos MySQL para guardar la información del sistema.

## Tecnologías

- PHP 8.1 o superior recomendado.
- MySQL o MariaDB.
- PDO para la conexión con la base de datos.
- HTML, CSS y JavaScript.
- XAMPP para ejecutar el proyecto localmente.

## Requisitos

- Apache.
- PHP 8.1 o superior recomendado.
- MySQL o MariaDB.
- Extensión PDO MySQL habilitada.
- Un navegador web actualizado.

## Instalación local con XAMPP

1. Descarga o clona el repositorio.
2. Coloca la carpeta del proyecto dentro del directorio web de XAMPP, normalmente `htdocs`.
3. Inicia Apache y MySQL desde el panel de XAMPP.
4. Abre phpMyAdmin e importa el archivo `database/classcheck.sql`.
5. Revisa `config/conexion.php` y configura el host, nombre de la base de datos, usuario y contraseña según tu instalación local.
6. Abre en el navegador `http://localhost/ClassCheck/crear_administrador.php`.
7. Crea la cuenta del primer administrador con una contraseña segura de al menos 14 caracteres.
8. Cuando se confirme la creación, elimina `crear_administrador.php` del directorio web.
9. Abre `http://localhost/ClassCheck/` e inicia sesión.

> Las rutas pueden variar según el nombre de la carpeta y la configuración local de XAMPP.

## Datos académicos

El registro de estudiantes solicita información como carrera, módulo y ciclo. Las cuentas docentes no utilizan esos mismos campos y pueden necesitar aprobación administrativa antes de tener acceso completo.

Las contraseñas se guardan mediante funciones de hash de PHP.

## Funciones pendientes y limitaciones

- Los formularios y procesos completos para registrar y modificar asistencia y calificaciones todavía deben implementarse y probarse con las reglas oficiales de la institución.
- La edición y eliminación de horarios necesitan completar sus flujos de envío y validación.
- La recuperación de contraseña por correo no está habilitada.
- El sistema requiere pruebas funcionales y de seguridad antes de cualquier despliegue real.

## Seguridad y uso responsable

- No publiques contraseñas reales ni credenciales de bases de datos en el repositorio.
- Los valores de `config/conexion.php` deben ajustarse para cada entorno y no deben contener secretos de producción.
- Antes de utilizar información real, configura HTTPS, respaldos, protección contra intentos repetidos de inicio de sesión y una gestión segura de credenciales.
- El archivo `database/classcheck.sql` puede eliminar tablas existentes de la base `classcheck`. Impórtalo únicamente en una base nueva o después de realizar un respaldo.
- No uses datos personales reales hasta completar las funciones pendientes y realizar una revisión de seguridad.

## Contribuciones

Si deseas contribuir, puedes crear una rama, realizar tus cambios y abrir una solicitud de incorporación (*pull request*) para su revisión.

## Licencia

La licencia del proyecto debe añadirse aquí cuando haya sido definida.
