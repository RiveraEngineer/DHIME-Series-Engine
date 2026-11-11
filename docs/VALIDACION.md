# Validación de DHIME Series Engine 1.0.0

Prueba de descarga: 9 de noviembre de 2026. Compilación del instalador: 11 de noviembre de 2026. Fechas en hora de Colombia.

Se probaron el visor, la descarga, las figuras y el instalador. La suite completa aprobó **642 pruebas, sin omisiones**, sobre el código con el que se compiló el instalador. Además, se realizó una descarga real desde el visor contra el servicio oficial.

## Descarga real desde el visor

Se añadieron **126 consultas** mediante **Agregar al lote** y se exportaron **124 series**. Para cada una se verificaron el CSV original, el ZIP, el Excel y la figura.

| Resultado | Alcance |
|---|---|
| 124 series exportadas | Precipitación, temperatura, humedad relativa, velocidad y dirección del viento, caudal y nivel, con los parámetros disponibles del plan de prueba. |
| 2 consultas pendientes | Temperatura del punto de rocío mínima diaria en San Bernardo (52045030) y Taminango (52045040). DHIME reportó disponibilidad, pero su servicio no completó la exportación. |

Cada consulta cubrió un año completo: **117 correspondieron a 2020, siete de viento a 2001 y dos de máximos de viento a 2014**, según la disponibilidad del plan. Se obtuvieron 124 Excel nativos y 133 figuras: 124 individuales, seis de viento y tres conjuntas de temperatura y humedad. Las figuras conjuntas utilizaron los archivos descargados, sin repetir consultas ni mezclar sus frecuencias.

Las dos exportaciones pendientes se informaron como errores del servicio. No se les asignó un porcentaje de faltantes ni se contaron como descargas correctas.

### Consulta de Aponte

Se consultó **Aponte (5204500108)** con su código exacto. No aparecieron series en las consultas de disponibilidad que respondieron. Dos configuraciones de velocidad vectorial diaria devolvieron un error HTTP 500 al consultar sus metadatos y siguen sin comprobar. Por ello, la prueba **no certifica ausencia total de datos** en esta estación ni la sustituye por otra.

## Concordancia del visor y los archivos

Se cotejaron los porcentajes y sus conteos en **las 124 series exportadas**, entre el resumen CSV, el JSON del ZIP, la hoja **Completitud** del Excel y la figura PNG. También se compararon **12 series representativas cargadas en el visor** con sus descargas: coincidieron el periodo, los registros esperados, los válidos, los faltantes y el porcentaje.

El análisis respeta el periodo solicitado, incluidos los extremos sin observaciones, los años bisiestos y las frecuencias mensuales o anuales. Sin filtro, utiliza las fechas disponibles reportadas para la serie. Cuenta valores numéricos finitos y únicos; los ceros son datos válidos. Los duplicados no aumentan la cobertura.

Si la frecuencia no está verificada, hay fechas inválidas o las horas no siguen una pauta comprobable, el resultado se muestra como **no calculable**. Una consulta fallida tampoco equivale a 100 % de datos faltantes. El cálculo no rellena, interpola ni cambia los valores originales.

Como comprobación adicional, la humedad relativa horaria de Antonio Nariño (52045020) durante 2020 tuvo **8.784 registros esperados, 1.096 válidos y 7.688 faltantes: 87,52 %**. La escasez de lecturas no se utilizó para cambiar la frecuencia horaria publicada.

Los derivados separan los faltantes de la serie calculada de los faltantes en sus datos de origen. Las comparativas y la figura conjunta conservan un indicador por serie. Las rosas cuentan pares compatibles de velocidad y dirección; una media mensual o anual no permite reconstruir la distribución horaria de un mes. Los casos sin datos suficientes se informan, en lugar de fabricar una rosa.

## Gráficas y consulta de valores

Se comprobó la selección de observaciones por clic y por fecha, sin interpolar ni consultar otra vez Internet. También se probaron el zoom, el cambio de tamaño y las escalas de pantalla de 100 %, 150 % y 200 %.

Las figuras del visor y de la descarga respetan los vacíos y las fechas originales. Las etiquetas del eje temporal ajustan su cantidad al espacio y al periodo visible. Los trazos escalares, las unidades y los registros se revisaron en las figuras generadas; las rosas conservan los colores de sus clases.

## Búsqueda desde una instalación limpia

El instalador incluye las fechas reportadas para **69.729 series de 6.376 estaciones**. El visor usa ese índice al buscar y consulta IDEAM automáticamente si la estación todavía no figura allí.

Se probó **Palmas (23190380, Lebrija)** con un perfil nuevo y sin acceso a la red durante la búsqueda. Al pulsar **Buscar** aparecieron las series de precipitación diaria, mensual y anual con sus fechas. Los otros cuatro parámetros se mostraron como pendientes de comprobar; con conexión, el visor los consulta al IDEAM sin que haya que pedirlo, y sin conexión conserva el listado del índice.

Al restablecer la conexión, **Ver gráfica** cargó la precipitación diaria de 2020 desde IDEAM. La gráfica registró **366 de 366 observaciones (0 % de faltantes)**. **Agregar al lote** conservó la estación, la serie y las fechas elegidas.

También se instaló el instalador encima de una instalación existente. Se comprobó de nuevo la búsqueda en el visor y se conservó el archivo de descarga de prueba.

## Instalador y limpieza

Se verificó el instalador para **Windows de 64 bits**, con sus componentes de Python incluidos. La aplicación instalada abrió su interfaz, cargó el catálogo y las ocho familias de variables, y realizó una descarga real de precipitación para Berruecos (52040160), del 1 al 3 de enero de 2020. Los valores **20,0; 1,5 y 1,4 mm** coincidieron con una consulta independiente a DHIME y con los archivos exportados.

La prueba de instalación se hizo en una carpeta aislada del usuario. La desinstalación retiró el programa y conservó una descarga de prueba. Se verificaron los recursos incluidos y el rechazo de un catálogo alterado. Las conexiones mantuvieron la validación de certificados y del nombre del servidor.

Al cerrar la aplicación se retiraron los recursos temporales de la prueba y su carpeta de certificados. Las descargas y figuras se conservaron. La prueba principal también cerró sus ventanas y procesos hijos y retiró sus preferencias y cachés aisladas.

La descarga de 126 consultas se hizo el 9 de noviembre, antes de los últimos ajustes de interfaz y del asistente de instalación. Esos ajustes no tocaron la descarga ni el tratamiento de los datos, y esa prueba no se repitió. Sobre el instalador publicado sí se hicieron la instalación limpia, la instalación encima de una existente, la desinstalación, el caso de Palmas y la descarga de Berruecos.

El navegador de respaldo no acepta certificados con errores. Ese camino solo se usa cuando el servicio directo no responde, y en estas pruebas no fue necesario recorrerlo porque todas se resolvieron por el servicio directo. Se comprobó aparte que el portal carga por HTTPS sin advertencias.

Las bibliotecas incluidas tienen versiones fijas. Una revisión del 11 de noviembre encontró avisos de seguridad publicados para Pillow 12.3.0, urllib3 2.7.0, certifi 2026.7.22 y filelock 3.32.6. La aplicación solo abre con Pillow las figuras que ella misma genera, y las consultas al IDEAM no pasan por urllib3 ni filelock. Su actualización queda para la siguiente versión.

El instalador **aún no tiene firma digital de editor**; su estado comprobado es **NotSigned**. La huella SHA-256 publicada permite contrastar el archivo, pero no sustituye una firma digital.

| Instalador | Bytes | SHA-256 |
|---|---:|---|
| DHIME_Series_Engine_1.0.0_Instalador.exe | 84,928,756 | `c79ab84f18fc8469c2834cd0a5ee07d760dde6b84fd3b8666a967a8ac023d12e` |

## Alcance de los resultados

Estas comprobaciones corresponden a las estaciones, parámetros y periodos probados. No aseguran que todas las estaciones del IDEAM tengan todas las variables ni que el servicio responda siempre. La disponibilidad y las revisiones de las observaciones dependen del IDEAM.

BART se utiliza para acelerar intervalos con equivalencia comprobada y vigente. DHIME conserva prioridad ante diferencias. La prueba no presupone que ambos repositorios sean idénticos para cualquier estación o fecha.

Esta validación corresponde a la versión **1.0.0**.
