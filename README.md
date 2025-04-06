# Configuracion de entorno python para el correcto funcionamiento
# 1: abrir una terminal en vscode y ejecutar lo siguiente 
python -m venv venv

venv\Scripts\activate
# 1.1: si el segundo comando falla ejecutar esta linea como admionistrador en windows powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser

# 2 una vez activado el entorno ejecutamos la instalacion nde librerias
pip install -r requirements.txt

# 3: LISTO!!! ya tienes configurado tu entorno

# TFM: Impacto del Cambio Climático a través de Indicadores de Desarrollo

## Introducción

El cambio climático es uno de los mayores desafíos del siglo XXI. Este trabajo fin de máster se centra en analizar cómo los indicadores económicos y de desarrollo de los países se relacionan con el cambio climático, poniendo especial atención en las emisiones de CO₂, las variaciones en la temperatura global y el potencial de las energías renovables para mitigar estos efectos.

## Motivación

El progreso humano, si bien ha traído innumerables beneficios, también ha contribuido significativamente al deterioro del medio ambiente. Este proyecto surge de la necesidad de comprender las interacciones entre el desarrollo económico y el impacto ambiental, y de evidenciar cómo la transición hacia fuentes de energía renovables puede representar una solución sostenible frente al calentamiento global.

## Objetivos

- **Analizar tendencias globales de emisiones de CO₂:** Investigar cómo varían las emisiones en función de los indicadores económicos y de desarrollo.
- **Explorar cambios en la temperatura global:** Evaluar la influencia de la actividad humana en las variaciones de la temperatura a nivel planetario.
- **Investigar el papel de las energías renovables:** Determinar el impacto de la adopción de energías renovables en la mitigación del cambio climático.
- **Relacionar indicadores de desarrollo y cambio climático:** Estudiar la correlación entre el desarrollo de un país y su contribución o vulnerabilidad frente al cambio climático.

## Metodología

Para alcanzar estos objetivos se realizará una integración y análisis de datos provenientes de fuentes internacionales reconocidas, tales como:

- **World Development Indicators (Banco Mundial):** Proporciona datos económicos y de desarrollo por país.
- **Emisiones de CO₂:** Datos disponibles en plataformas como Kaggle que permiten rastrear las emisiones a lo largo del tiempo.
- **Cambios en la temperatura:** Series históricas de datos de temperatura para evaluar tendencias.
- **Energías renovables:** Estadísticas y reportes de organismos como IRENA que analizan la penetración de energías limpias en la matriz energética.

Se utilizarán técnicas de análisis exploratorio y modelado estadístico para detectar patrones y relaciones significativas entre estas variables.

## Estructura del Proyecto

- **Documentación:** Este README y otros documentos que explican la justificación y el alcance del proyecto.
- **Datos:** Conjunto de datos recopilados de diversas fuentes internacionales, organizados y documentados para facilitar su análisis.
- **Análisis:** Scripts y notebooks en Python que contienen el procesamiento, análisis y visualización de los datos.
- **Resultados:** Sección dedicada a la interpretación de los hallazgos y la discusión sobre su implicancia en el debate del cambio climático.
- **Conclusiones y Recomendaciones:** Reflexiones finales y sugerencias de políticas públicas y acciones futuras basadas en los resultados obtenidos.

## Requisitos y Ejecución

Para replicar y extender el análisis del proyecto se recomienda contar con:

- **Librerías:** 
  - Pandas
  - NumPy
  - Pymysql
  - Otras dependencias que se especificarán en un archivo `requirements.txt`

Iutilización de entornos virtuales y Jupyter Notebook o JupyterLab para explorar y ejecutar los scripts de análisis.

## Conclusión

Este TFM tiene como propósito aportar una visión multidimensional sobre el cambio climático, combinando análisis de indicadores económicos y ambientales para fundamentar la importancia de una transición hacia energías renovables. Se espera que los resultados obtenidos ofrezcan una base sólida para la formulación de estrategias de mitigación y adaptación ante los efectos del calentamiento global.

## Contacto

Para dudas, comentarios o colaboraciones, por favor contacta con el autor del proyecto.

*Este proyecto se desarrolla como parte del Trabajo Fin de Máster en INESDI.*
