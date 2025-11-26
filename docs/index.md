**Universidad de Costa Rica** | Escuela de Ingeniería Eléctrica  
*IE0405 - Modelos Probabilísticos de Señales y Sistemas*  
Profesores: Fabián Abarca Calderón y Sebastián Ramírez Sandí  
Asistente: Darío Guzmán Carranza  
Segundo ciclo de 2025

# Proyecto de programación  
## Análisis Estadístico de la Variación Temporal en Lecturas de Sensor

---

## Estudiante
- **Karla Méndez**, B84870 – Grupo 2

---

## Resumen

Este proyecto analiza el comportamiento temporal de un sistema de adquisición de datos provenientes de un sensor físico. El objetivo principal es evaluar si los intervalos de tiempo entre muestras consecutivas (Δt) se distribuyen de manera exponencial, lo cual es característico de procesos de Poisson en sistemas de llegada o captura de eventos.

Para ello, se llevó a cabo:

- Recolección automática de datos desde un script en Python.  
- Almacenamiento estructurado en una base de datos SQLite.  
- Limpieza, preparación y ordenamiento temporal de las muestras.  
- Cálculo de diferencias temporales entre eventos (Δt).  
- Análisis estadístico descriptivo.  
- Ajuste de una distribución exponencial y estimación del parámetro λ.  
- Visualización mediante histogramas y superposición del modelo teórico.

Toda la documentación técnica del proceso se detalla en las siguientes secciones:

---

## Secciones

### 🔹 [Introducción](introduccion.md)
Descripción general del sistema, motivación y planteamiento del problema.

### 🔹 [Metodología](metodologia.md)
Fuente de los datos, cliente MQTT, almacenamiento, ordenamiento temporal y procesamiento.

### 🔹 [Resultados](resultados.md)
Estadísticas descriptivas, histogramas, ajuste exponencial y validación visual.

### 🔹 [Distribución](distribucion.md)
Justificación del modelo estadístico, función de densidad, parámetro λ y propiedades relevantes.

### 🔹 [Conclusiones](conclusiones.md)
Hallazgos principales, limitaciones y consideraciones finales.

---

Este sitio fue generado con **MkDocs + Material for MkDocs**.
