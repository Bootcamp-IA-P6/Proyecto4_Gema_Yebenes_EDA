# 📊 Análisis Exploratorio de COVID-19 en Estados Unidos

> Un recorrido por la evolución temporal y geográfica de la pandemia (2020-2021)

---

## 📋 Tabla de Contenidos

- [Descripción](#-descripción-del-proyecto)
- [Objetivos](#-objetivos)
- [Estructura del Proyecto](#-estructura-del-proyecto)
- [Tecnologías Utilizadas](#-tecnologías-utilizadas)
- [Instalación](#-instalación-rápida)
- [Uso](#-guía-de-uso)
- [Dataset](#-información-del-dataset)
- [Análisis Realizado](#-análisis-realizado)
- [Reportes](#-reportes-generados)
- [Comandos Útiles](#-comandos-útiles-con-uv)
- [Contribuciones](#-contribuir)
- [Licencia](#-licencia)

---

## 🎯 Descripción del Proyecto

Este proyecto realiza un **análisis exploratorio de datos (EDA)** completo sobre la evolución del COVID-19 en Estados Unidos durante el período 2020-2021. A través de técnicas de ciencia de datos y visualización, se exploran patrones, tendencias y insights clave sobre el comportamiento de la pandemia.

El análisis incluye la limpieza y preprocesado de datos, exploración de variables clave, y generación de visualizaciones profesionales para comunicar los hallazgos de manera efectiva.

---

## 🎯 Objetivos

- **Comprender** la estructura y calidad del dataset histórico de COVID-19
- **Limpiar** y preprocesar los datos para garantizar su validez
- **Analizar** la evolución temporal de casos, fallecimientos y hospitalizaciones
- **Visualizar** patrones y tendencias de manera clara y profesional
- **Generar** insights accionables sobre el comportamiento de la pandemia
- **Documentar** todo el proceso de análisis de forma reproducible

---

## 📁 Estructura del Proyecto

```
PROYECTO_4_EDA/
│
├── 📂 data/
│   └── all-states-history.csv          # Dataset con 20,780 registros históricos
│
├── 📓 notebooks/
│   └── 01_eda_covid_usa.ipynb          # Notebook principal con análisis EDA completo
│
├── 📊 reports/
│   ├── 01_eda_covid_usa.html           # Reporte interactivo en formato HTML
│   └── Informe_Final_EDA_Covid.pdf     # Informe profesional en PDF
│
├── 🐍 main.py                           # Script principal de ejecución
│
├── ⚙️  .python-version                  # Versión de Python del proyecto
├── 📦 pyproject.toml                    # Configuración del proyecto y dependencias
├── 🔒 uv.lock                           # Lock file para reproducibilidad exacta
├── 🙈 .gitignore                        # Archivos excluidos del control de versiones
│
└── 📖 README.md                         # Este archivo
```

---

## 🛠 Tecnologías Utilizadas

### Lenguaje
- **Python 3.11** - Lenguaje principal del proyecto

### Análisis de Datos
- **Pandas** - Manipulación y análisis de datos estructurados
- **NumPy** - Operaciones numéricas y computación científica

### Visualización
- **Matplotlib** - Creación de gráficos y visualizaciones estáticas
- **Seaborn** - Visualizaciones estadísticas de alto nivel

### Entorno de Desarrollo
- **Jupyter Notebook** - Análisis interactivo y documentación
- **IPython** - Shell interactivo mejorado

### Gestión de Paquetes
- **UV** - Gestor de paquetes y entornos virtuales ultrarrápido

---

## 🚀 Instalación Rápida

### Prerequisitos

Solo necesitas tener instalado **UV** en tu sistema. 

> **⚠️ Nota Importante**: La instalación de UV se hace **una sola vez en tu ordenador**, no por proyecto. Si ya tienes UV instalado, salta directamente a la [Instalación del Proyecto](#instalación-del-proyecto).

#### Instalar UV (Solo la primera vez)

**macOS / Linux:**
```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

**Windows (PowerShell):**
```bash
powershell -c "irm https://astral.sh/uv/install.ps1 | iex"
```

### Instalación del Proyecto

Una vez tengas UV instalado en tu sistema (solo primera vez), para cualquier proyecto:

```bash
# 1. Clonar el repositorio
git clone https://github.com/Bootcamp-IA-P6/Proyecto4_Gema_Yebenes_EDA.git
cd PROYECTO_4_EDA

# 2. Instalar uv 
pip install uv

# 3. Sincronizar el proyecto (instala todo automáticamente)
uv sync
```

**¡Eso es todo!** 🎉 

El comando `uv sync` se encarga de:
- ✅ Crear el entorno virtual `.venv/` automáticamente
- ✅ Instalar Python en la versión especificada (si no lo tienes)
- ✅ Instalar todas las dependencias del `pyproject.toml`
- ✅ Generar el archivo `uv.lock` para reproducibilidad exacta

---

## 💻 Guía de Uso

### Ejecutar el Notebook Principal

**Opción 1: Usando UV (Recomendado)**
```bash
uv run jupyter notebook
```
> No necesitas activar el entorno virtual. UV lo hace automáticamente.

**Opción 2: Activando el entorno manualmente**
```bash
# Activar el entorno virtual
source .venv/bin/activate  # macOS/Linux
 souurce .venv\Scripts\activate # Windows

# Ejecutar Jupyter
jupyter notebook
```

Una vez abierto Jupyter:
1. Navega a `notebooks/01_eda_covid_usa.ipynb`
2. Ejecuta las celdas secuencialmente usando `Shift + Enter`
3. Explora los análisis, visualizaciones y resultados

### Ejecutar el Script Principal

```bash
# Con UV (recomendado)
uv run python main.py

# O con el entorno activado
python main.py
```

---

## 📊 Información del Dataset

### Características Generales

| Propiedad | Detalle |
|-----------|---------|
| **Nombre del archivo** | `all-states-history.csv` |
| **Período cubierto** | Enero 2020 - Marzo 2021 |
| **Total de registros** | 20,780 filas |
| **Variables totales** | 41 columnas |
| **Cobertura geográfica** | 50 estados + DC + territorios de EE.UU. |
| **Frecuencia** | Datos diarios |

### Variables Principales

#### 📅 Temporales y Geográficas
- `date` - Fecha del registro (formato YYYY-MM-DD)
- `state` - Código del estado (2 letras)

#### 🦠 Casos y Fallecimientos
- `positive` - Casos positivos acumulados
- `positiveIncrease` - Incremento diario de casos positivos
- `death` - Fallecimientos acumulados
- `deathIncrease` - Incremento diario de fallecimientos
- `deathConfirmed` - Fallecimientos confirmados por laboratorio
- `deathProbable` - Fallecimientos probables

#### 🏥 Hospitalización
- `hospitalized` - Hospitalizaciones acumuladas
- `hospitalizedCurrently` - Pacientes hospitalizados actualmente
- `hospitalizedIncrease` - Incremento de hospitalizaciones
- `inIcuCurrently` - Pacientes en unidad de cuidados intensivos
- `onVentilatorCurrently` - Pacientes con ventilador mecánico

#### 🧪 Testing y Pruebas
- `totalTestResults` - Total de pruebas realizadas
- `totalTestResultsIncrease` - Incremento diario de pruebas
- `positiveTestsViral` - Pruebas virales positivas
- `negativeTestsViral` - Pruebas virales negativas
- `totalTestsAntibody` - Total de pruebas de anticuerpos
- `totalTestsAntigen` - Total de pruebas de antígenos

### Notas Importantes sobre los Datos

⚠️ **Valores Nulos**: Varias columnas contienen valores nulos, especialmente en variables de testing específico

⚠️ **Heterogeneidad**: Diferentes estados reportan datos con distintos niveles de detalle

⚠️ **Metodologías**: Las metodologías de reporte pueden variar entre estados

⚠️ **Completitud**: Algunos estados tienen registros más completos que otros

---

## 🔬 Análisis Realizado

El notebook incluye las siguientes etapas de análisis:

### 1. Exploración Inicial del Dataset
- Carga de datos desde archivo CSV
- Visualización de primeras filas
- Análisis de dimensiones (20,780 × 41)
- Identificación de tipos de datos
- Generación de estadísticas descriptivas

### 2. Preparación y Transformación de Datos
- Conversión de columna `date` a formato datetime
- Ordenamiento cronológico de registros
- Análisis de valores nulos por variable
- Validación de transformaciones realizadas

### 3. Análisis Exploratorio de Datos
- Evolución temporal de casos positivos
- Tendencias de fallecimientos
- Patrones de hospitalización
- Análisis de pruebas realizadas
- Comparativas entre estados

### 4. Visualizaciones y Presentación
- Gráficos de series temporales
- Tablas con estilos CSS personalizados
- Scroll horizontal para mejor visualización
- Diseño profesional con paleta corporativa

---

## 📑 Reportes Generados

El proyecto genera reportes en múltiples formatos ubicados en la carpeta `reports/`:

### 🌐 Reporte HTML
**Archivo:** `01_eda_covid_usa.html`

Versión interactiva del análisis que puede visualizarse directamente en cualquier navegador web. Incluye:
- Código ejecutable
- Resultados de análisis
- Visualizaciones interactivas
- Estilos CSS personalizados

### 📕 Informe PDF
**Archivo:** `Informe_Final_EDA_Covid.pdf`

Documento profesional listo para presentaciones o entregas formales. Incluye:
- Resumen ejecutivo
- Metodología aplicada
- Hallazgos principales
- Conclusiones y recomendaciones

### 📓 Notebook Jupyter
**Archivo:** `notebooks/01_eda_covid_usa.ipynb`

Análisis completo reproducible paso a paso, ideal para:
- Revisión técnica detallada
- Modificación y extensión del análisis
- Aprendizaje y documentación del proceso

---

## 🎓 Características Destacadas

### Estilos Personalizados
El notebook incluye estilos CSS profesionales que mejoran significativamente la presentación:
- Tablas con scroll horizontal automático
- Diseño corporativo con paleta de colores elegante
- Tipografía moderna y legible
- Efectos hover para mejor interactividad

---

## 👤 Autor

**Gema Yébenes**

- GitHub: https://github.com/gemayc
- LinkedIn: https://www.linkedin.com/in/gemayebenes-tech/

---

**Desarrollado con ❤️ usando Python y UV**

