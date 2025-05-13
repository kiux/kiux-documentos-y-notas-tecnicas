# Configuración de Delphi para OAuth2

# [Crear la cuenta de servicio para Google API y crear credenciales](Service_Account_google_API.md)

# Instalar librerías necesarias

1. En "jwt.io", selecciona Delphi y copia la ruta de la librería en gitHub.

2. Instala la librería "jwt" en Delphi.

   2.1 Descarga la librería desde el repositorio de GitHub. Code > Download ZIP.

   2.2 Descomprime el archivo ZIP y copia la carpeta "jwt" en la carpeta de tu proyecto o en una carpeta de librerías de Delphi.

   2.3 Abre el proyecto en Delphi, ve a la carpeta Pakages en la carpeta de la libreria, selecciona la versión de Delphi que estás utilizando y abre el archivo .dpk correspondiente.

   2.4 _Construir e instalar el paquete._

   2.4.1 Abre el menú "Component" y selecciona "Install Packages".

   2.4.2 Cambia el "Build Configuration" a "Release".

   2.4.3 Selecciona options > description > Usage option y selecciona "Desing and runtime".

   2.4.4 Selecciona el paquete que acabas de instalar y haz clic derecho sobre el y selecciona "Build" (soluciona los problemas si aparecen y realiza el "Build" para las diferentes plataformas).

   2.4.5 Haz clic derecho nuevamente y selecciona "Install".

   2.5 _Configura el path de la librería en Delphi_

   2.5.1 Abre el menú "Tools" y selecciona "Options".

   2.5.2 Selecciona Languaje > Delphi > Library > "Library Path".

   2.5.3 Selecciona la plataforma que estás utilizando (Win32, Win64, Android, iOS) o agregalo para todas.

   2.5.4 Agrega la ruta de la carpeta donde copiaste la librería "jwt" (Deberá estar en la carpeta de la libreria + ./lib/<-plataforma->/release/).

3. Recuerda que la librería "JOSE" requiere de los dll "libeay32.dll" y "ssleay32.dll" para funcionar correctamente. Asegúrate de que estos archivos estén en la misma carpeta que tu ejecutable o en una carpeta del sistema.

# Configuración de las credenciales

1. Convierte la "private key" del archivo JSON a un formato adecuado para Delphi. Puedes usar una herramienta en línea o un script para hacer esto.
   - Asegúrate de que la clave esté en formato PEM y que las líneas de inicio y fin sean correctas.
   - La clave debe verse así:
     ```
     -----BEGIN PRIVATE KEY-----
       <private_key>
       -----
         END PRIVATE KEY-----
     ```
   - Luego lo conviertes en string en base 64 y lo guardas donde corresponda.
