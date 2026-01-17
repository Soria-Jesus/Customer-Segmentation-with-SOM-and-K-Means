# Customer Segmentation with SOM and K-Means

## 📌 Descripción del proyecto

En este proyecto se realiza un análisis de **segmentación de clientes** a partir de un conjunto de datos que contiene información sociodemográfica, de consumo y comportamiento de compra de clientes de una empresa de retail.

El flujo de trabajo incluye una fase de **exploración, limpieza y transformación de datos**, seguida por la aplicación de un **Self-Organizing Map (SOM)** para reducir la dimensionalidad de los datos preservando su estructura topológica. Posteriormente, se utiliza el algoritmo **K-Means** sobre los pesos del SOM para definir los clusters finales.

El objetivo principal es **identificar segmentos de clientes con características y patrones de comportamiento similares**, que puedan servir como apoyo para el diseño de **estrategias de marketing, ventas y fidelización más efectivas y personalizadas**.

---

## 📂 Dataset

El dataset contiene información de clientes de una compañía de retail, incluyendo variables:

* Sociodemográficas (edad, nivel educativo, estado civil, tamaño de la familia)
* Económicas (ingreso anual)
* De consumo (gasto por tipo de producto)
* De comportamiento de compra (canales utilizados, visitas web)
* De respuesta a campañas promocionales

Durante el proyecto se realizaron tareas de **imputación de valores faltantes**, **ingeniería de características** y **limpieza de datos**, generando variables adicionales como:

* `Age`
* `Children`
* `Is_Parent`
* `Family_Size`
* `Total_Spent`

El archivo del dataset se encuentra en la carpeta `data/`.

---

## 🛠️ Instalación y requisitos

Para ejecutar este proyecto se requiere:

* Python 3.9 o superior
* Jupyter Notebook o Jupyter Lab

### Instalación de dependencias

Las librerías necesarias se encuentran listadas en el archivo `requirements.txt`.

Puedes instalarlas ejecutando el siguiente comando desde la raíz del proyecto:

```bash
pip install -r requirements.txt

```  

## ⚙️ Metodología

El proceso de análisis se desarrolló en las siguientes etapas:

1. **Exploratory Data Analysis (EDA)**
   Análisis descriptivo de las variables para entender su distribución, detectar valores atípicos y conocer relaciones iniciales entre características.

2. **Preprocesamiento de datos**

   * Imputación de valores faltantes
   * Eliminación de variables no relevantes para el clustering
   * Ingeniería de nuevas variables
   * Escalamiento de las variables numéricas mediante *StandardScaler*

3. **Reducción de dimensionalidad con Self-Organizing Map (SOM)**
   Se entrenó un SOM bidimensional para proyectar los datos de alta dimensionalidad a una grilla 2D, preservando la topología de los datos.
   Posteriormente, se construyó un **grafo ponderado** a partir de los pesos del SOM y se calcularon los **Best Matching Units (BMU)** para cada observación.

4. **Clustering con K-Means**
   El algoritmo **K-Means** se aplicó sobre los pesos del SOM para definir los clusters finales.
   El número de clusters se seleccionó utilizando el **método del codo** sobre la inercia.

5. **Asignación de clusters y análisis**
   Cada cliente fue asignado al cluster correspondiente de su BMU.
   Finalmente, se realizó un análisis detallado de los clusters mediante visualizaciones estadísticas y comparativas.

---

## 📊 Resultados e Insights

El análisis permitió identificar **cuatro clusters bien diferenciados**, con diferencias claras en:

* Nivel de ingreso
* Patrón de gasto total y por tipo de producto
* Composición familiar
* Canales de compra preferidos
* Sensibilidad a campañas promocionales

De manera general, se observó que **a mayor ingreso, mayor gasto**, especialmente en productos como vinos y productos premium.
Cada cluster presenta un perfil específico que puede ser aprovechado para **segmentación estratégica y personalización de campañas**.

Los insights detallados por cluster se encuentran documentados dentro del notebook en la sección *Insights finales por cluster*.

---

## 🧰 Librerías utilizadas

* `numpy`
* `pandas`
* `matplotlib`
* `seaborn`
* `scikit-learn`
* `minisom`
* `networkx`

---

## 📫 Contacto

**Jesús Armando Soria Martínez**

📧 Email: oficial.jasm@gmail.com  
💼 [LinkedIn](http://www.linkedin.com/in/jesus-armando-soria-martinez-a9b786366)

---
