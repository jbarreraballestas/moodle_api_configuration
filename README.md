# moodle_api_configuration Probada en Moodle 3.11.5+
## Ayuda con la configuración de moodle para acceso via web service/api


## Identificado como usuario administrador: 

**Administracion servicios web**

- Administración del sitio > Servidor > Servicios Web

**Paso 1. Habilitar Servicios Web**

- Asegurese de que los servicios web esten habilitados

**Paso 2. Habilitar los protocolos**

- Asegurese de que el protocolo REST este habilitado

**Paso 3. Crear un usuario específico**

- Cree un usuario para administrar el servicio web, todas las solicitudes se realizaran con este usuario

**Paso 4. Comprobar privilegios del usuario**

- Agregar un nuevo rol para conceder el permiso webservice/rest:use

Administración del sitio > Usuarios > Permisos > Definir roles > Gestionar roles > Añadir un nuevo rol

> **Nombre corto:** API REST

> **Tipos de contexto en que puede asignarse este rol:** Sistema

> **Usar protocolo REST webservice/rest:use:** Permitir

- Asignar el rol creado al usuario para acceso

Administración del sitio > Usuarios > Permisos > Asignar roles de sistema > API REST

Busque el usuario que creó y dele agregar
