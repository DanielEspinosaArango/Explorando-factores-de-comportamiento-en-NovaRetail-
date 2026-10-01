# NovaRetail+ Customer Behavior Analysis

Este repositorio contiene el análisis de los factores de comportamiento de los clientes realizado para **NovaRetail+**, una plataforma de comercio electrónico en Latinoamérica.

El análisis busca identificar **qué factores del comportamiento de los clientes están más asociados con el ingreso anual**, utilizando 15,000 registros de clientes y técnicas de análisis exploratorio, correlación y asociación entre variables.

---

## 📂 Contenido del repositorio

```text
📁 novaretail-analysis/
├── 📄 README.md                          ← Estás aquí
├── 📓 novaretail_behavior_analysis.ipynb
│   → Notebook principal con análisis completo
│   → Exploración, estadísticas, correlaciones y conclusiones
├── 📊 data/
│   └── novaretail_comportamiento_clientes_2024.csv
│       → Dataset con información de 15,000 clientes
└── 📈 outputs/
    └── ...
```

---

## ▶ Cómo abrir el notebook en Google Colab

**Opción 1 - Click directo:**

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](URL_DEL_NOTEBOOK_EN_GITHUB)

**Opción 2 - Manual:**

1. Ve al repositorio en GitHub.
2. Abre el archivo `novaretail_behavior_analysis.ipynb`.
3. Haz clic en el botón **"Open in Colab"** en la parte superior del notebook.

---

## 📘 Cómo reproducir el análisis

### Requisitos

* Python 3.8+
* Jupyter Notebook o Google Colab
* Librerías:

  * `pandas`
  * `numpy`
  * `matplotlib`
  * `seaborn`
  * `scipy`

### Pasos para ejecutar

1. **Abre el notebook** en Google Colab utilizando el enlace anterior.
2. **Ejecuta las celdas en orden**.
3. El notebook carga el dataset de NovaRetail+.
4. Ejecuta las secciones de exploración, visualización y análisis de correlaciones.
5. Revisa los resultados y conclusiones al final del notebook.

El dataset utilizado contiene información sobre características demográficas, comportamiento de compra, satisfacción, membresía, dispositivo, región e ingreso anual.

---

## 🎯 Objetivo del análisis

NovaRetail+ necesitaba **entender qué comportamientos de sus clientes están más relacionados con el ingreso anual** para identificar oportunidades de negocio y orientar futuras estrategias comerciales.

### Preguntas clave que respondemos:

✔ **¿Qué comportamiento presenta la mayor asociación con el ingreso anual?**

* `compras_mes` presenta la asociación más fuerte.
* Correlación de Pearson: **0.9671**.
* La relación es positiva y muy fuerte.

✔ **¿Las visitas mensuales están relacionadas con los ingresos?**

* `visitas_mes` presenta una asociación positiva, pero mucho menor.
* Correlación de Pearson: **0.3371**.

✔ **¿El gasto en publicidad dirigida está asociado con mayores ingresos?**

* La asociación es positiva, pero débil.
* Correlación de Pearson: **0.1975**.

✔ **¿La satisfacción del cliente está relacionada con el ingreso anual?**

* La asociación es prácticamente nula.
* Correlación de Pearson: **0.0562**.

✔ **¿La membresía premium genera diferencias importantes?**

* La asociación entre membresía premium e ingreso anual es débil.
* Correlación punto-biserial: **0.0931**.

✔ **¿Existen asociaciones entre variables categóricas?**

* La relación entre `region` y `tipo_dispositivo` es prácticamente nula.
* V de Cramér: **0.0124**.

---

## 📊 Hallazgos principales

### Relación entre compras e ingreso anual

| Variable                    | Correlación con ingreso_anual | Interpretación          |
| --------------------------- | ----------------------------: | ----------------------- |
| `compras_mes`               |                    **0.9671** | Muy fuerte y positiva   |
| `visitas_mes`               |                    **0.3371** | Débil/moderada positiva |
| `gasto_publicidad_dirigida` |                    **0.1975** | Débil positiva          |
| `satisfaccion`              |                    **0.0562** | Prácticamente nula      |

La frecuencia de compras es, con diferencia, la variable que presenta la mayor asociación con el ingreso anual.

El análisis también muestra un **R² aproximado de 0.94** para la relación entre compras mensuales e ingreso anual.

⚠️ Debido a la magnitud excepcional de esta relación, es necesario **auditar la relación entre ambas variables** para determinar si existe redundancia o algún vínculo directo en la construcción de los datos.

---

### Comportamiento de los clientes

El dataset contiene **15,000 clientes y 12 variables**.

Entre las principales características observadas:

* Edad promedio: aproximadamente **38 años**.
* Visitas mensuales promedio: aproximadamente **10**.
* Compras mensuales promedio: **1.21**.
* Satisfacción promedio: **3.60/5**.
* El ingreso anual presenta una dispersión elevada.

---

### Uso de dispositivos

El dispositivo más utilizado es el **móvil**, representando aproximadamente:

* 📱 Móvil: **65.45%**
* 💻 Escritorio: **24.80%**
* 📱 Tablet: **9.75%**

Esto indica una fuerte predominancia del canal móvil dentro de la base de clientes.

---

### Membresía Premium

La membresía premium presenta asociaciones débiles con las principales variables de comportamiento:

* Premium vs. `ingreso_anual`: **0.0931**
* Premium vs. `compras_mes`: **0.0034**
* Premium vs. `visitas_mes`: **-0.0127**

Los resultados no muestran una diferenciación clara entre clientes premium y no premium en términos de comportamiento.

---

### Región y dispositivo

La asociación entre `region` y `tipo_dispositivo`, medida mediante **V de Cramér**, fue:

**0.0124**

Esto indica una asociación prácticamente nula entre ambas variables.

---

## 💡 Recomendaciones ejecutivas

### Corto plazo (0-3 meses)

1. **Auditar la relación entre compras e ingreso anual**

   * Validar la definición y construcción de ambas variables.
   * Determinar si existe redundancia o una relación directa entre ellas.

2. **Priorizar estrategias orientadas a aumentar la frecuencia de compra**

   * Incentivos de recompra.
   * Campañas de conversión.
   * Estrategias de fidelización.

3. **Optimizar la experiencia móvil**

   * El móvil representa aproximadamente el 65% del uso.
   * Revisar navegación, proceso de compra y experiencia de usuario.

### Mediano plazo (1-6 meses)

4. **Analizar la conversión de visitas en compras**

   * Las visitas presentan una asociación mucho menor con el ingreso.
   * Es importante estudiar qué factores convierten tráfico en compras.

5. **Revisar la propuesta de valor del programa Premium**

   * La membresía no presenta una asociación fuerte con ingresos o compras.
   * Analizar beneficios, adopción y comportamiento de los miembros.

6. **Profundizar el análisis de satisfacción**

   * La relación con ingreso anual es prácticamente nula.
   * Validar si la métrica utilizada representa adecuadamente la experiencia del cliente.

---

## 🔧 Tecnologías utilizadas

* **Python 3.x**
* **Pandas** - Manipulación y análisis de datos
* **NumPy** - Cálculos numéricos
* **Seaborn & Matplotlib** - Visualización de datos
* **SciPy** - Análisis estadístico y correlaciones
* **Google Colab / Jupyter Notebook** - Ejecución del análisis

---

## 📝 Estructura del análisis

```text
PASO 1: Carga y exploración
├─ Importar librerías
├─ Cargar dataset
└─ Revisar estructura y primeras observaciones

PASO 2: Exploración de datos
├─ Identificar tipos de variables
├─ Revisar valores faltantes
└─ Analizar estadísticas descriptivas

PASO 3: Análisis de variables numéricas
├─ Edad
├─ Visitas mensuales
├─ Compras mensuales
├─ Gasto en publicidad
├─ Satisfacción
└─ Ingreso anual

PASO 4: Análisis de relaciones
├─ Correlación de Pearson
├─ Correlación de Spearman
├─ Correlación punto-biserial
└─ V de Cramér

PASO 5: Visualizaciones
├─ Histogramas
├─ Gráficos de dispersión
├─ Matrices de correlación
└─ Visualizaciones categóricas

PASO 6: Interpretación
├─ Identificar asociaciones relevantes
├─ Comparar magnitud de relaciones
├─ Analizar patrones de comportamiento
└─ Identificar posibles problemas de redundancia

PASO 7: Análisis ejecutivo
├─ Principales hallazgos
├─ Limitaciones
├─ Oportunidades
└─ Recomendaciones de negocio
```

---

## 👥 Autor

Análisis realizado como parte del proceso de formación en **Data Analytics**.

**Proyecto: Explorando factores de comportamiento en NovaRetail+**

---

## 📚 Datos

* **Dataset:** `novaretail_comportamiento_clientes_2024.csv`
* **Clientes:** 15,000
* **Variables:** 12
* **Periodo:** 2024
* **Sector:** Comercio electrónico
* **Cobertura:** Clientes de NovaRetail+ en Latinoamérica
* **Variable objetivo:** `ingreso_anual`

---

## 📞 Contacto

Si tienes preguntas, comentarios o sugerencias sobre este análisis, puedes abrir un **Issue** en el repositorio.
