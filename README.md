# Configuración API / Web Service Educativo Probada en versión 3.11.5+

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
> 
> **Tipos de contexto en que puede asignarse este rol:** Sistema
> 
> **Usar protocolo REST webservice/rest:use:** Permitir

- Asignar el rol creado al usuario para acceso

Administración del sitio > Usuarios > Permisos > Asignar roles de sistema > API REST

Busque el usuario que creó y dele agregar

- Asegurese de que el usuario tiene el permiso Usar protocolo REST webservice/rest:use Sí

**Paso 5. Seleccione un servicio**

Administración del sitio > Servidor > Servicios Web > Seleccione un servicio > Agregar 

> **Nombre:** servicioejemplo
> 
> **Habilitado:** Sí
> 
> **Únicamente usuarios autorizados:** Sí

Guardar

**Paso 6. Agregar funciones**

Administración del sitio > Servidor > Servicios Web > Agregar funciones > Servicios personalizados > servicioejemplo > Funciones > Agregar funciones

Busque las funciones que su servicio web / api usara y de click en agregar funciones

**Paso 7. Seleccione un usuario específico**

Administración del sitio > Servidor > Servicios Web > Seleccione un usuario específico > Servicios personalizados > servicioejemplo > Usuarios autorizados

Busque y agregue el usuario que hará uso del web service / api

**Paso 8. Crear ficha (token) para un usuario**

Administración del sitio > Servidor > Servicios Web > Crear ficha (token) para un usuario > 

> **Usuario:** usuarioapi
> 
> **Servicio:** servicioejemplo
> 
> **Restricción de IP:** 127.0.0.1

Reemplaze la ip por la dirección ip pública desde donde se lanzaran las solicitudes al servicio web / api

Guarda el token para realizar la prueba

**Paso 10. Comprobar el servicio**

Administración del sitio > Servidor > Servicios Web > Comprobar el servicio

> **Método de identificación** token
> 
> **Protocolo** Protocolo REST
> 
> **Función** core_webservice_get_site_info
>
> **token** 369e4e79c4b91c129ecce82d8513e9d7

Reemplaza el token por el generado para tu usuario, ejecutamos y listo

**Inicio de sesión desde otro sistema - Nota: Esto abre una brecha de seguridad pero permite hacer login desde apps externas [mas info](https://docs.moodle.org/dev/Login_token)**

Agregar 
```
$CFG->disablelogintoken = true;
```
en **config.php**

Ya estamos listos para comenzar el desarrollo de nuestro producto que hará uso de este web service

