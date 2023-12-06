# APICORE

API-BANK
Preparativos
SQL Server
Crear una base de datos utilizando el script ubicado en la carpeta "ScriptAPI" del proyecto.

Proyecto
En el archivo appsettings.json del proyecto, ajustar la cadena de conexión a la base de datos según sea necesario. La cadena tiene el siguiente formato:

json
Copy code
"ConexionSqlServer": "Server=DESKTOP-9E12MUD\\SQLEXPRESS;Database=Bank;Trusted_Connection=True;MultipleActiveResultSets=true;TrustServerCertificate=true;"
Importante
El puerto en las URLs puede cambiar.

Se recomienda realizar el LOGIN en la página "Swagger" al ejecutar el proyecto y revisar el puerto mostrado en la información para utilizarlo en las demás peticiones.

Actualmente, en la base de datos existen 2 usuarios autorizados:

Usuario: james@gmail.com / Contraseña: 1234
Usuario: carlos@gmail.com / Contraseña: 1234
Estos son los únicos usuarios autorizados actualmente. Para agregar otros, se debe hacer directamente en la base de datos.

Autenticación
Para realizar cualquier petición en la API, es necesario generar un token mediante el login de la siguiente manera:

Enviar una solicitud POST a la siguiente URL: https://localhost:44392/Login
En el cuerpo de la petición, ingresar las credenciales registradas en la base de datos en formato JSON:
json
Copy code
{
  "email": "carlos@gmail.com",
  "pwd": "1234"
}
La respuesta de la petición será el token necesario para realizar las demás acciones de la API:

json
Copy code
{
  "$id": "1",
  "token": "eyJhbGciOiJodHRwOi8vd3d3LnczLm9yZy8yMDAxLzA0L3htbGRzaWctbW9yZSNobWFjLXNoYTI1NiIsInR5cCI6IkpXVCJ9.eyJodHRwOi8vc2NoZW1hcy54bWxzb2FwLm9yZy93cy8yMDA1LzA1L2lkZW50aXR5L2NsYWltcy9uYW1lIjoiQ2FybG9zIiwiaHR0cDovL3NjaGVtYXMueG1sc29hcC5vcmcvd3MvMjAwNS8wNS9pZGVudGl0eS9jbGFpbXMvZW1haWxhZGRyZXNzIjoiY2FybG9zQGdtYWlsLmNvbSIsImV4cCI6MTcwMTQ4NDc5Mn0.smMOE9b10HlyfXA9VbT82gHHQQ6A2aOGsB9liHirKtA"
}
Para realizar el resto de las peticiones, es necesario utilizar el token generado:

Ir al apartado de Authorization.
Seleccionar Bearer.
Ingresar el token.
Para obtener detalles sobre las demás peticiones, consultar la documentación de la API proporcionada.
