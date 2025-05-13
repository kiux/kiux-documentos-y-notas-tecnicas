# Configuración de la cuenta de servicio para Google API y delegación de dominio amplia

Para utilizar la API de Google (como la API de Gmail) en el formato Server to Server, necesitas configurar una cuenta de servicio y habilitar la delegación de dominio amplia. Aquí te dejo los pasos para hacerlo:

# Creación de "Service Account" para Google API y creación de credenciales

1. Ve a la consola de Google Cloud: https://console.cloud.google.com/
2. Crea un nuevo proyecto o selecciona uno existente.
3. Habilita la API de Gmail:
   - Ve a "API & Services" > "Library".
   - Busca "Gmail API" y haz clic en "Enable".
4. Ve a "API & Services" > "Credentials".
5. Haz clic en "Create Credentials" y selecciona "Service Account".
6. Completa los detalles de la cuenta de servicio (nombre, ID, etc.).
7. En la sección "Service Account Permissions", selecciona el rol "Project" > "Editor" o "Owner".
8. Haz clic en "Done" para crear la cuenta de servicio.
9. En la lista de cuentas de servicio, selecciona la cuenta que acabas de crear.
10. En la sección "Keys", haz clic en "Add Key" y selecciona "JSON". Esto descargará un archivo JSON con las credenciales de la cuenta de servicio.
11. Guarda el archivo JSON en un lugar seguro, ya que contiene la clave privada de la cuenta de servicio.

# Delegación de dominio amplio (Domain-Wide Delegation)

1. Se debe pedir al administrador de Google Workspace que habilite la delegación de dominio amplia para la cuenta de servicio.
2. Debes habilitar la delegación de dominio amplia en la consola de Google Admin. Esto permite que la cuenta de servicio actúe en nombre de los usuarios de tu dominio.
3. En la consola de Google Admin, ve a "Security" > "API Controls" > "Manage Domain Wide Delegation".
4. Agrega un nuevo cliente y proporciona el Client ID de la cuenta de servicio y los scopes necesarios (por ejemplo, `https://www.googleapis.com/auth/gmail.send`).
