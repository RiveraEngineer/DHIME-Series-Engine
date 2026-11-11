# Autoría, fuentes y créditos

Esta página reconoce a quienes aportan los datos, servicios y bibliotecas que utiliza la herramienta.

## Herramienta

**DHIME Series Engine — autoría y mantenimiento: Sergio Alejandro Rivera Monroy.**

ORCID: [0009-0003-5470-8856](https://orcid.org/0009-0003-5470-8856).
GitHub: [RiveraEngineer](https://github.com/RiveraEngineer).

La cita del software se encuentra en [CITAR.md](CITAR.md) y sus metadatos en [CITATION.cff](CITATION.cff).

## Datos y servicios oficiales

El **Instituto de Hidrología, Meteorología y Estudios Ambientales (IDEAM)** proporciona los datos y los servicios consultados:

- [DHIME](https://atencionciudadano.ideam.gov.co/): disponibilidad y exportación de series; referencia ante diferencias.
- [BART / AQTSUtils](https://bart.ideam.gov.co/PQRS/AQTSUtils/): descargas que aceleran únicamente los intervalos con equivalencia comprobada y vigente.

La herramienta es independiente de IDEAM. Este reconocimiento no implica respaldo institucional ni transfiere la autoría de los datos. Sus condiciones de acceso, uso y cita se conservan.

## Bibliotecas utilizadas

Las bibliotecas mantienen sus autores y licencias. El instalador incluye los componentes necesarios y conserva sus textos y avisos en la carpeta **Avisos_Terceros** de la aplicación instalada. La lista siguiente reconoce usos directos representativos y no reemplaza esos avisos completos.

| Proyecto | Uso en la herramienta | Documentación y licencia |
|---|---|---|
| Python y Tkinter | Ejecución e interfaz de escritorio | [Python](https://www.python.org/), [licencia](https://docs.python.org/3/license.html) |
| pandas | Tablas y tratamiento de series | [pandas](https://pandas.pydata.org/), [licencia](https://github.com/pandas-dev/pandas/blob/main/LICENSE) |
| NumPy | Operaciones numéricas | [NumPy](https://numpy.org/), [licencia](https://github.com/numpy/numpy/blob/main/LICENSE.txt) |
| Matplotlib | Figuras y rosas de viento | [Matplotlib](https://matplotlib.org/), [licencia](https://matplotlib.org/stable/project/license.html) |
| openpyxl | Archivos Excel | [openpyxl](https://openpyxl.readthedocs.io/), [licencia](https://openpyxl.readthedocs.io/en/stable/licence.html) |
| certifi | Certificados CA para verificar conexiones TLS | [certifi](https://github.com/certifi/python-certifi), [licencia MPL-2.0](https://github.com/certifi/python-certifi/blob/master/LICENSE) |
| HTTPX | Consultas HTTP directas de DHIME | [HTTPX](https://www.python-httpx.org/), [licencia](https://github.com/encode/httpx/blob/master/LICENSE.md) |
| Playwright | Consulta de respaldo mediante navegador | [Playwright para Python](https://playwright.dev/python/), [licencia](https://github.com/microsoft/playwright-python/blob/main/LICENSE) |
| Pillow | Lectura y presentación de imágenes | [Pillow](https://python-pillow.github.io/), [licencia](https://github.com/python-pillow/Pillow/blob/main/LICENSE) |
| Hugging Face Hub | Gestión de archivos y repositorios | [Hugging Face Hub](https://huggingface.co/docs/huggingface_hub/), [licencia](https://github.com/huggingface/huggingface_hub/blob/main/LICENSE) |
| Boto3 | Acceso a almacenamiento compatible con S3 | [Boto3](https://boto3.amazonaws.com/v1/documentation/api/latest/index.html), [licencia](https://github.com/boto/boto3/blob/develop/LICENSE) |

La distribución también conserva los avisos de **Python (PSF), Tcl/Tk y OpenSSL**, así como los de **PyInstaller**, utilizado para preparar el ejecutable, y **NSIS**, utilizado para el asistente de instalación. Se incluyen sus textos de licencia y la excepción del cargador de PyInstaller, además de los avisos de las dependencias transitivas.

## Proyectos evaluados en la revisión del acceso a datos

Se reconocen como antecedentes técnicos:

- **David De Leon Perez** ([ORCID 0000-0002-1846-9750](https://orcid.org/0000-0002-1846-9750)), autor de [ideam-dhime](https://github.com/David-R-De-Leon-P/IDEAM_scrapping), disponible también en [PyPI](https://pypi.org/project/ideam-dhime/) y publicado con licencia GPL-3.0-or-later. DOI [10.5281/zenodo.19740803](https://doi.org/10.5281/zenodo.19740803). Se revisó su interfaz de Python sobre Selenium/Chrome y su descarga por lotes.
- **Sergio Beltrán Coley** (Universidad de la Costa, Barranquilla), autor de [IDEAM Data Automator](https://github.com/sergiobc27/ideam-data-automator), publicado con licencia Apache-2.0. DOI [10.5281/zenodo.20562858](https://doi.org/10.5281/zenodo.20562858). Se revisó su enfoque de extracción HTTP mediante Socrata.

Quien cite DHIME Series Engine y quiera reconocer estos antecedentes debe citarlos con los datos que cada autor publica en su repositorio.

**No se incorporó código de esos dos proyectos en DHIME Series Engine.** El 11 de noviembre de 2026 se comparó el código de la versión 1.0.0 con ideam-dhime 0.3.0 e IDEAM Data Automator 1.2.3 y no se encontraron bloques de código en común. No son dependencias de esta distribución ni autores del servicio HTTP oficial de IDEAM. Sus autores, código y licencias se consultan en los enlaces originales. La equivalencia de sus sensores y parámetros con DHIME no se presupone.

La herramienta consulta el servicio oficial de IDEAM y comprueba la estación, el parámetro, las unidades, las fechas y los campos de calidad.

## Alcance de este reconocimiento

El catálogo de estaciones, los datos de contraste, las instantáneas del portal y los demás datos o documentos procedentes de IDEAM conservan su atribución y condiciones originales. Estos créditos no modifican las licencias de las dependencias ni las condiciones de los datos. La solicitud de cita académica del software es independiente de la licencia.

## Licencia del proyecto

La licencia MIT se aplica a la aplicación, que se distribuye como instalador, y a la documentación propia de DHIME Series Engine. El código fuente no se publica en este repositorio. Los datos, catálogos, instantáneas y documentos procedentes de IDEAM y los componentes de terceros conservan sus derechos y condiciones respectivos; esta licencia no otorga derechos adicionales sobre ellos.

El texto está en [MIT](LICENSE). La cita académica se solicita separadamente y no añade restricciones a esa licencia. Las licencias y avisos de las dependencias deben conservarse cuando corresponda a su redistribución.
