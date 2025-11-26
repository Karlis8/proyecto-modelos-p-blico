# Metodología

La metodología aplicada en este proyecto se divide en estas etapas principales: captura de datos, almacenamiento, preparación, análisis estadístico y visualización.

---

## 1. Captura y almacenamiento de datos

Los datos fueron recolectados mediante un script en Python (`client.py`) que se mantuvo suscrito a un tópico MQTT específico asociado al sensor.
Cada vez que se recibía un nuevo mensaje, este era decodificado y almacenado en una base de datos SQLite junto con su marca temporal (`timestamp`).

Este mecanismo permitió:

- Evitar pérdida de datos por interrupciones.
- Mantener un registro ordenado y persistente.
- Facilitar el análisis posterior mediante consultas SQL.

La captura se ejecutó durante más de tres horas continuas, cumpliendo el requisito del proyecto. Durante ese periodo, cada lectura fue registrada correctamente en la tabla `events`.

---

## 2. Extracción y preparación de los datos

Una vez completada la recopilación, los datos fueron procesados con `pandas` siguiendo los pasos:

1. Lectura de la tabla completa desde `data.db`.
2. Ordenamiento ascendente por `timestamp`.
3. Conversión precisa de marcas de tiempo a objetos (segundos) `datetime`.
4. Cálculo de Δt utilizando `diff()` para obtener:
$$
\[
\Delta t_i = t_{i} - t_{i-1}
\]
$$
5. Eliminación de valores nulos o inconsistentes.
6. Exportación opcional a CSV para verificación manual.

---
### Modelo de la Base de Datos

Para el almacenamiento se utilizó *SQLite* junto con *SQLAlchemy*. La estructura de la tabla utilizada es la siguiente:
```python
from sqlalchemy import Column, Integer, String, DateTime
from sqlalchemy.orm import declarative_base

Base = declarative_base()

class Event(Base):
    __tablename__ = "events"

    id = Column(Integer, primary_key=True)
    mqtt_id = Column(String)
    first_name = Column(String)
    last_name = Column(String)
    timestamp = Column(DateTime)

```
Esta tabla almacena cada evento recibido del sensor, identificando al usuario y registrando el instante exacto de llegada.
---


## 3. Análisis estadístico

Conlos valores de Δt calculados se obtuvo estadísticas descriptivas, media, mediana, desviación estándar, mínimo, máximo y cuartiles. También se evaluó si los tiempos entre llegadas se comportaban según una distribución exponencial, modelo común para procesos de Poisson.
El parámetro de la exponencial se estimó por máxima verosimilitud:
$$
\[
\lambda = \frac{1}{\bar{\Delta t}}
\]
$$

Este valor representa la tasa promedio de ocurrencia de eventos.
---

## 4. Visualización

Se generaron dos figuras principales para interpretar el comportamiento de los datos:

1. **Histograma de Δt**, mostrando la distribución empírica.  
2. **Histograma + curva exponencial teórica**, donde se supone:

\[
f(x) = \lambda e^{-\lambda x}
\]

Estas visualizaciones permiten comparar directamente el modelo teórico con los datos observados.
Ambas figuras se encuentran en la carpeta `images/` y se discuten con detalle en la sección de Resultados.