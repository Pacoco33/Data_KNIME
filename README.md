# Data_KNIME
Análisis de datos con KNIME

# Análisis y Agrupamiento de Animes por País con KNIME

Este proyecto nace de una pregunta bastante simple pero interesante:  
**¿Qué animes son los más populares en distintos países, y cómo se relacionan entre sí?**

Usando la plataforma KNIME, analizamos un dataset con los animes más vistos por país, aplicamos técnicas de agrupamiento (clustering), entrenamos un modelo de predicción y, de forma indirecta, también abrimos la puerta a posibles recomendaciones.

# ¿Qué hace este workflow?

El flujo de trabajo está dividido en varias partes:

1. **Carga y limpieza de datos**
   - Leemos el archivo ".csv" con la información de visualización por país.
   - Eliminamos columnas innecesarias y tratamos valores nulos para dejar todo listo.

2. **Agrupamiento (clustering)**
   - Usamos dos técnicas:
     - "K-Means": agrupa los datos en k grupos (por ejemplo, tipos de popularidad).
     - "DBSCAN": detecta agrupaciones según densidad, muy útil para encontrar patrones más libres (y outliers).
   - Esto nos permite ver qué animes o países tienen comportamientos similares.

3. **Predicción con Random Forest**
   - Se entrena un modelo que puede predecir a qué grupo pertenece un nuevo dato.
   - Esto podría servir, por ejemplo, para anticipar cómo sería recibido un nuevo anime en ciertos países.

4. **Visualización y evaluación**
   - Creamos gráficas para ver los grupos formados.
   - Evaluamos la calidad del agrupamiento con el coeficiente de silueta (entre más alto, mejor agrupados están).

# ¿Y esto es un recomendador?

Más o menos sí.

Aunque no estamos diciendo “si viste este anime, te gustará este otro”, con este workflow:

- Podrías usar los grupos creados para **sugerir animes populares en otros países similares al tuyo**.
- O incluso **recomendar animes nuevos** basándote en el grupo al que probablemente pertenezcan.
- No es un sistema de recomendación completo, pero sí una muy buena base para uno.
