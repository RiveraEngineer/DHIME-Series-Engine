# Instalación y comprobación del archivo

## Comprobar la descarga

El instalador pesa 84,928,756 bytes y su huella SHA-256 es

    c79ab84f18fc8469c2834cd0a5ee07d760dde6b84fd3b8666a967a8ac023d12e

Para calcularla en tu equipo abre PowerShell en la carpeta donde quedó el archivo y ejecuta

    Get-FileHash .\DHIME_Series_Engine_1.0.0_Instalador.exe -Algorithm SHA256

El resultado debe ser igual al de arriba, sin importar mayúsculas. Si es distinto, el archivo se dañó al bajar o no es el que se publicó aquí. Bórralo y descárgalo otra vez desde este repositorio.

La huella dice que el archivo no cambió desde que se publicó. No reemplaza una firma digital.

## El aviso de Windows

El instalador no está firmado con un certificado de editor. Conseguir uno exige un trámite de validación de identidad que todavía no se ha hecho. Mientras tanto, Windows SmartScreen puede mostrar «Windows protegió su PC» la primera vez.

Después de comprobar la huella

1. pulsa «Más información»,
2. revisa que el nombre del archivo sea el mismo que descargaste,
3. pulsa «Ejecutar de todas formas».

Si tu antivirus pone el archivo en cuarentena, no lo desactives. Compara la huella y, si coincide, repórtalo en los [issues](https://github.com/RiveraEngineer/DHIME-Series-Engine/issues) con el nombre del antivirus y el mensaje que dio.

En las propiedades del archivo, pestaña «Detalles», deben aparecer el producto DHIME Series Engine, la versión 1.0.0 y el autor.

## Qué hace el instalador

- Copia la aplicación en `%LOCALAPPDATA%\Programs\DHIME Series Engine`. Puedes elegir otra carpeta.
- Crea el acceso en el menú Inicio y, si lo marcas, en el escritorio.
- Registra el desinstalador para tu usuario.

No pide permisos de administrador, no instala servicios, no se inicia con Windows y no modifica otros programas. Incluye su propio intérprete de Python, que solo usa la aplicación.

Las preferencias (idioma, modo oscuro, última carpeta) se guardan en `%APPDATA%\DHIME_Series_General`.

## Conexiones que hace la aplicación

Solo se conecta por HTTPS, con validación de certificados, a los servicios del IDEAM y, una vez al abrir, a GitHub para saber si hay una versión nueva.

| Servidor | Para qué |
|---|---|
| modulopersonalizado.ideam.gov.co | Disponibilidad y exportación de series (DHIME) |
| atencionciudadano.ideam.gov.co | Portal DHIME en Chrome, como respaldo |
| bart.ideam.gov.co | Archivos consolidados que aceleran algunas consultas |
| api.github.com | Número de la última versión publicada de este repositorio |

No hay cuentas ni telemetría. La consulta a GitHub es anónima y solo lee el número de la última versión; si hay una más reciente aparece un botón que abre su página. La aplicación no descarga ni instala actualizaciones por su cuenta y no envía información tuya ni de tu equipo.

## Actualizar

Cuando la aplicación avise que hay una versión nueva, descarga su instalador desde la página que abre el botón. Cierra la aplicación y ejecuta el instalador nuevo sobre la instalación existente. Si la aplicación está abierta, el asistente te pedirá cerrarla.

## Desinstalar

Desde Configuración de Windows, Aplicaciones, o con «Desinstalar» en el grupo del menú Inicio. Se retiran los archivos de la aplicación y sus accesos. Tus descargas se quedan donde las guardaste.
