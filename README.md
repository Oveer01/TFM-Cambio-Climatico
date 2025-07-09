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
├── data/                          # Conjunto de datos originales y procesados
│   ├── API_AG.LND.TOTL2_DS2_en_excel_v2_85542.xls
│   ├── API_NY.GDP.MKTP.CD_DS2_en_excel_v2_85096.xls
│   ├── API_SP.POP.TOTL_DS2_en_excel_v2_85347.xls
│   ├── Environment_Temperature_change_E_All_Data_NOFLAG.csv
│   ├── FAOSTAT_data_1-10-2022.csv
│   ├── FAOSTAT_data_11-24-2020.csv
│   ├── FAOSTAT_data_en_11-1-2024.csv
│   ├── P_Data_Extract_From_World_Development_Indicators.xlsx
│   ├── Pa_sos.csv
│   └── tidy_format_co2_emission_dataset.csv
│
├── docs/                          # Documentación y diagramas
│   ├── BBDD_Cambio_climatico.xlsx
│   ├── DiagramaEntidadRelacion.png
│   └── Primera_entrega_TFM_Diccionario_de_datos.docx
│
├── notebooks/                     # Notebooks de análisis y carga de datos
│   ├── analisis/                  # Exploración y mapeo de datos
│   │   └── mapeado_de_datos.ipynb
│   ├── creacion/                  # Scripts para generar la base de datos
│   │   └── crear_base_datos.ipynb
│   └── insercion/                 # Inserción de datos por dominio
│       ├── 01_insertar_datos_paises.ipynb
│       ├── 02_insertar_datos_temperatura.ipynb
│       ├── 03_insertar_datos_emisionesCO2.ipynb
│       ├── 04_insertar_datos_economicos.ipynb
│       └── 05_insertar_datos_demograficos.ipynb
|       └── 06_insertar_datos_catastrofes_ naturales.ipynb
│
├── .env.example                   # Ejemplo de variables de entorno
├── .gitignore                     # Archivos y carpetas ignorados por Git
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
  Ejecutar secuencialmente los notebooks en `notebooks/insercion/`:

  1. `01_insertar_datos_paises.ipynb`
  2. `02_insertar_datos_temperatura.ipynb`
  3. `03_insertar_datos_emisionesCO2.ipynb`
  4. `04_insertar_datos_economicos.ipynb`
  5. `05_insertar_datos_demograficos.ipynb`
  6. `06_insertar_datos_catastrofes_naturales.ipynb`


* **Análisis exploratorio**:
  Abrir `notebooks/analisis/mapeado_de_datos.ipynb` para visualizar, limpiar y combinar los datos.

---

## 🎯 Objetivos y metodología

* **Análisis de emisiones de CO₂** en función de indicadores económicos y demográficos.
* **Evaluación de series de temperatura** para identificar tendencias globales.
* **Impacto de energías renovables** en la mitigación del cambio climático.
* **Relaciones estadísticas** entre desarrollo socioeconómico y vulnerabilidad/clima.

Los datos provienen de fuentes como World Bank (WDI), FAOSTAT, Kaggle, y reportes de IRENA. Se emplean técnicas de análisis exploratorio y modelado estadístico en Python (pandas, NumPy, SQLAlchemy, etc.).

---

*Este proyecto forma parte del Trabajo Fin de Máster en INESDI.*
