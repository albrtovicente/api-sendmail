# Enviar email

## Api
 Un programa para enviar un correo
## Descripcion
 Se puede enviar correos ingresando 3 variables
    - name: nombre del usuario
    - email: correo del destinatario
    - message: el mensaje a enviar
 Toda la funcion es programado en index.php y probado en sendmail.http
## Instalacion
pasos de instalacion:
  -  Copiar el código: guardandolo en un archivo en su servidor.
  - Configuración del correo : Abra el archivo PHP y edite la variable $webmaster_email para reemplazarla con la dirección de correo electrónico del webmaster donde desea recibir los mensajes del formulario de contacto.
  - Implementar en su sitio web o aplicación: Incluya el archivo PHP en su sitio web o aplicación web en la página donde desea que aparezca el formulario de .
## Uso (endpoint, parámetros)
 - Endpoint: El script espera recibir una solicitud POST a la URL donde se encuentra el archivo PHP.

- Parámetros: Los datos del formulario de contacto se envían en el cuerpo de la solicitud en formato JSON. Los parámetros JSON esperados son:second

## Ejemplo de solicitud (cliente http, formulario o react)

POST http://localhost/api/v1/endpoint-webservice/index.php
Content-Type: "application/json"

{
    "name": "alberto",
    "email":"alberto@gmail.com",
    "message":"mldkvnsvskv"
}

### respuesta
{
  "status": "success",
  "message": "Correo enviado correctamente."
}

### Respuesta
{
  "status": "error",
  "message": "Datos inv\u00e1lidos."
}


### Prueba de correo con un dato faltante
POST http://localhost/api/v1/endpoint-webservice/index.php
Content-Type: "application/json"

{
    "name": "alberto",
    "email":"",
    "message":"mldkvnsvskv"
}
### EXITOSO

### Respuesta
{
  "status": "error",
  "message": "Datos inv\u00e1lidos."
}

### Prueba de correo con todos los datos faltantes
POST http://localhost/api/v1/endpoint-webservice/index.php
Content-Type: "application/json"

{
    "name": "",
    "email":"",
    "message":""
}
### EXITOSO
### Respuesta
{
  "status": "error",
  "message": "Datos inv\u00e1lidos."
}