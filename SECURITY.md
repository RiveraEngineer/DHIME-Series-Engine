# Seguridad

## Reportar un problema

Si encuentras una falla de seguridad en la aplicación o en el instalador, escríbeme por un aviso privado de GitHub (pestaña Security del repositorio, «Report a vulnerability»). Si no puedes usar esa vía, abre un issue que diga solo que quieres reportar un problema de seguridad y te contacto.

Incluye la versión, la huella SHA-256 del instalador que usaste y los pasos para reproducirlo. Respondo en cuanto pueda. Es un proyecto personal, sin tiempos garantizados.

## Versiones

Se corrige la versión publicada más reciente.

## Cómo está protegida la distribución

- El instalador se publica con su huella SHA-256. La forma de comprobarla está en [docs/INSTALACION.md](docs/INSTALACION.md).
- Al iniciar, la aplicación instalada compara las huellas de sus catálogos e índices con un manifiesto incluido en el ejecutable. Si un recurso fue alterado, no abre.
- Las dependencias se instalan en la compilación con versiones fijas y huellas verificadas.
- Las conexiones son HTTPS a servidores del IDEAM, con validación de certificado y de nombre de servidor. No se siguen redirecciones en las consultas directas.
- El aviso de versión nueva hace una consulta anónima a GitHub y solo acepta enlaces a la página de versiones de este repositorio. No descarga ni ejecuta nada.
- La distribución pública no contiene credenciales ni usa cuentas.

El instalador todavía no tiene firma Authenticode. Está pendiente.
