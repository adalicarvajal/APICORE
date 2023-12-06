# APICORE

## Preparativos

### SQL Server
Para comenzar, asegúrate de tener SQL Server instalado. Crea una base de datos ejecutando el script ubicado en la carpeta "ScriptAPI" del proyecto.

## Configuración del Proyecto

En el archivo `appsettings.json` del proyecto, ajusta la cadena de conexión a la base de datos según tus necesidades. La cadena tiene el siguiente formato:

```json
"ConexionSqlServer": "Server=DESKTOP-9E12MUD\\SQLEXPRESS;Database=Bank;Trusted_Connection=True;MultipleActiveResultSets=true;TrustServerCertificate=true;"

