# TFM: Impacto del Cambio Climático a través de Indicadores de Desarrollo

![Python](https://img.shields.io/badge/python-3.9%2B-blue.svg) ![Licencia](https://img.shields.io/badge/licencia-MIT-green.svg)

**Equipo:**
- Rafael Jesús Cadavieco Guiral  
- Javier Calle Olivier  
- Karla Lorena Figueroa Contreras  
- Conrado Cristian Hidalgo Gutiérrez  
- David Pino Peña  

Este repositorio contiene el proyecto del Trabajo Fin de Máster (TFM) titulado **"Impacto del Cambio Climático a través de Indicadores de Desarrollo"**. El objetivo es integrar y analizar datos de distintas fuentes para explorar la relación entre indicadores económicos, emisiones de CO₂, variaciones de temperatura y la adopción de energías renovables.

---

## 📁 Estructura del proyecto

```
TFM-CAMBIO-CLIMATICO/
│
├── data/                          # Datos del proyecto
│   ├── fuentes/                   # Datos fuente para extracción de valores
│   │   ├── climaticos/            # Datos de temperatura, clima y emisiones
│   │   │   ├── EDGAR_2024_GHG_booklet_2024.xlsx          # Emisiones GHG por país (EDGAR 2024)
│   │   │   ├── Environment_Temperature_change_E_All_Data_NOFLAG.csv  # Cambios de temperatura
│   │   │   ├── FAOSTAT_data_1-10-2022.csv                # Datos climáticos FAOSTAT
│   │   │   ├── FAOSTAT_data_11-24-2020.csv               # Datos climáticos FAOSTAT
│   │   │   ├── FAOSTAT_data_en_11-1-2024.csv             # Datos climáticos FAOSTAT (actualizado)
│   │   │   ├── Indicator_11_1_Physical_Risks_Climate_related_disasters_frequency_7212563912390016675.csv  # Desastres climáticos
│   │   │   └── tidy_format_co2_emission_dataset.csv      # Dataset CO2 en formato tidy
│   │   │
│   │   ├── demograficos/          # Datos demográficos (población, superficie)
│   │   │   ├── API_SP.POP.TOTL_DS2_en_excel_v2_85347.xls     # Población total por país
│   │   │   └── API_AG.LND.TOTL.K2_DS2_en_excel_v2_85542.xls  # Superficie terrestre por país
│   │   │
│   │   ├── economicos/            # Datos económicos (PIB, indicadores de desarrollo)
│   │   │   ├── API_NY.GDP.MKTP.CD_DS2_en_excel_v2_85096.xls  # PIB por país
│   │   │   └── P_Data_Extract_From_World_Development_Indicators.xlsx  # Indicadores de desarrollo mundial
│   │   │
│   │   └── paises/                # Datos de países y códigos
│   │       └── Pa_sos.csv         # Referencia de países y códigos ISO
│   │
│   └── visualizacion/             # Datos para visualizaciones y gráficos
│       └── ne_50m_admin_0_countries/  # Archivos geoespaciales para mapas de países
│           ├── ne_50m_admin_0_countries.cpg
│           ├── ne_50m_admin_0_countries.dbf
│           ├── ne_50m_admin_0_countries.prj
│           ├── ne_50m_admin_0_countries.README.html
│           ├── ne_50m_admin_0_countries.shp
│           ├── ne_50m_admin_0_countries.shx
│           └── ne_50m_admin_0_countries.VERSION.txt
│
├── docs/                          # Documentación y diagramas
│   ├── BBDD Cambio climatico.xlsx                        # Esquema de base de datos
│   ├── diccionario_datos.txt                             # Diccionario de datos
│   ├── Modelo_Datos_TFM.docx                             # Modelo de datos del TFM
│   └── Primera entrega TFM_ Diccionario de datos.docx    # Primera entrega del diccionario
│
├── notebooks/                     # Notebooks de análisis y carga de datos
│   ├── analisis/                  # Exploración y análisis de datos
│   │   ├── 01_analisis_emisiones_economia.ipynb          # Análisis de emisiones y economía
│   │   ├── 02_analisis_temperatura_global.ipynb          # Análisis de temperatura global
│   │   └── 03_analisis_desarrollo_energias_renovables.ipynb  # Análisis de desarrollo y energías renovables
│   │
│   ├── creacion/                  # Scripts para generar la base de datos
│   │   └── crear_base_datos.ipynb                        # Creación de esquema de BD
│   │
│   ├── inserccion/                # Inserción de datos por dominio
│   │   ├── 01_insertar_datos_paises.ipynb                # Inserción de datos de países
│   │   ├── 02_insertar_datos_temperatura.ipynb           # Inserción de datos de temperatura
│   │   ├── 03_insertar_datos_emisionesCO2.ipynb          # Inserción de datos de emisiones CO2
│   │   ├── 04_insertar_datos_economicos.ipynb            # Inserción de datos económicos
│   │   ├── 05_insertar_datos_demograficos.ipynb          # Inserción de datos demográficos
│   │   └── 06_insertar_datos_catastrofes_ naturales.ipynb # Inserción de datos de catástrofes naturales
│   │
│   └── visualizacion/             # Notebooks para generar visualizaciones específicas
│       ├── 01_visualizacion_emisiones_economia.ipynb     # Visualizaciones de emisiones y economía
│       ├── 02_visualizacion_temperatura_global.ipynb     # Visualizaciones de temperatura global
│       ├── 03_visualizacion_desarrollo_renovables.ipynb  # Visualizaciones de desarrollo y renovables
│       └── visualizacion_tem_co2.ipynb                   # Visualización combinada temperatura-CO2
│
├── .env.example                   # Ejemplo de variables de entorno
├── .gitignore                     # Archivos y carpetas ignorados por Git
├── LICENSE                        # Licencia del proyecto
├── requirements.txt               # Dependencias del proyecto
└── README.md                      # Documentación principal
```

---

## 🚀 Instalación y configuración

1. **Clonar el repositorio**

   ```bash
   git clone https://github.com/Oveer01/TFM-Cambio-Climatico.git
   cd TFM-Cambio-Climatico
   ```

2. **Crear y activar un entorno virtual** (recomendado Python 3.9+):

   * En Windows PowerShell:

     ```powershell
     python -m venv venv
     .\venv\Scripts\Activate.ps1
     # Si falla por políticas de ejecución:
     Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
     .\venv\Scripts\Activate.ps1
     ```

   * En macOS/Linux:

     ```bash
     python3 -m venv venv
     source venv/bin/activate
     ```

3. **Instalar dependencias**

   ```bash
   pip install --upgrade pip
   pip install -r requirements.txt
   ```

4. **Variables de entorno**

   * Copiar `.env.example` a `.env` y completar con tus credenciales.

---

## 🛠️ Uso

* **Preparar la base de datos**:

  1. Configurar cadena de conexión en `.env`.
  2. Ejecutar el notebook `notebooks/creacion/crear_base_datos.ipynb` para crear las tablas.

* **Cargar datos**:
  Ejecutar secuencialmente los notebooks en `notebooks/inserccion/`:

  1. `01_insertar_datos_paises.ipynb`
  2. `02_insertar_datos_temperatura.ipynb`
  3. `03_insertar_datos_emisionesCO2.ipynb`
  4. `04_insertar_datos_economicos.ipynb`
  5. `05_insertar_datos_demograficos.ipynb`
  6. `06_insertar_datos_catastrofes_naturales.ipynb`


* **Análisis exploratorio**:
  - `notebooks/analisis/01_analisis_emisiones_economia.ipynb` para analizar tendencias globales de emisiones de CO₂ y su relación con indicadores económicos.
  - `notebooks/analisis/02_analisis_temperatura_global.ipynb` para explorar el impacto del cambio climático en la temperatura del planeta.
  - `notebooks/analisis/03_analisis_desarrollo_energias_renovables.ipynb` para examinar cómo los indicadores de desarrollo afectan al cambio climático y el papel de las energías renovables.

* **Visualizaciones**:
  - Ejecutar los notebooks en `notebooks/visualizacion/` para generar gráficos y visualizaciones específicas.
  - Las visualizaciones utilizan datos de `data/visualizacion/` para crear mapas interactivos y representaciones gráficas avanzadas.

---

## 🎯 Objetivos y metodología

Los objetivos principales de este TFM son:

1. **Analizar tendencias globales de emisiones de CO₂ y su relación con indicadores económicos**

2. **Explorar el impacto del cambio climático en la temperatura del planeta**

3. **Explorar cómo afectan los diferentes indicadores de desarrollo de un país en el cambio climático y evaluar el papel de las energías renovables**

Los datos provienen de fuentes como World Bank (WDI), FAOSTAT, Kaggle, y reportes de IRENA. Se emplean técnicas de análisis exploratorio y modelado estadístico en Python (pandas, NumPy, SQLAlchemy, etc.).

---

*Este proyecto forma parte del Trabajo Fin de Máster en INESDI.*
