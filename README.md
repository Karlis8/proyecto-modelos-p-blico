# Proyecto de Programación — IE0405  
## Análisis Estadístico de la Variación Temporal en Lecturas de Sensor  
**Universidad de Costa Rica – Escuela de Ingeniería Eléctrica**  

---

## Autora
- **Karla Méndez Sánchez**  
- Carné **B84870** — Grupo 2  

---

Los archivos incluidos en el repositorio original son:

- `mkdocs.yml`: configuración de la documentación en Material for MkDocs. Para más detalles, ver su [documentación](https://squidfunk.github.io/mkdocs-material/).
- `pyproject.toml`: especificación del proyecto y de las dependencias de paquetes de Python.
- `LICENSE`: licencia Creative Commons [Zero v1.0 Universal](https://creativecommons.org/publicdomain/zero/1.0/deed.es) de derechos de autor.
- `.gitignore`: archivos y directorios que Git ignora para hacer control de versiones y para subir a un repositorio remoto. Típicamente son archivos con datos privados o específicos del sistema operativo local, que no deben reproducirse en el repositorio de otros desarrolladores.
- `uv.lock`: parámetros del entorno de Python que será ejecutado con `uv` (más información en la [documentación de uv](https://docs.astral.sh/uv/)).
---
##  Descripción del Proyecto

Este proyecto implementa un sistema completo de adquisición, almacenamiento y análisis estadístico de eventos provenientes de un sensor físico.  

El objetivo principal es estudiar los **intervalos de tiempo entre lecturas consecutivas (Δt)** para evaluar si siguen una **distribución exponencial**, característica de los procesos de Poisson.

La solución final incluye:

- Cliente MQTT en Python que escucha eventos en tiempo real  
- Almacenamiento persistente mediante SQLite  
- Procesamiento y limpieza de datos  
- Análisis estadístico con Python  
- Visualización (histogramas + curva exponencial ajustada)  
- Prueba de bondad de ajuste (Kolmogorov–Smirnov)  
- Documentación completa generada con **MkDocs + Material**

---

## Tecnologías Utilizadas

- **Python 3.12**  
- **uv** (para entornos virtuales + ejecución de scripts)  
- SQLite  
- Paho-MQTT  
- Pandas, NumPy  
- Matplotlib  
- SciPy  
- MkDocs + Material for MkDocs  

---

## Instalación 
Este proyecto utiliza **uv**, un gestor ultrarrápido de entornos virtuales y dependencias en Python.

### 1. Clonar el repositorio
```bash
git clone https://github.com/improbabilidades/proyecto-Karlis8.git
cd proyecto-Karlis8
```
### 2. Crear el entorno virtual (con uv)
```bash
uv venv .venv
```
### 3. Activar el entorno
```bash
.\.venv\Scripts\activate
```
### 4. Instalar dependencias
```bash
uv pip install -r requirements.txt
```
---
## Ejecución del sistema
### 1. **Ejecutar el cliente MQTT**: Este script escucha el tópico del proyecto y almacena los eventos en `data.db`.
```bash
uv run client.py
```
El sistema debe ejecutarse mínimo 3 horas para recolectar suficientes datos (requisito del curso).
### 2. Ejecutar el análisis estadístico
```bash
uv run analisis.py
```
Este script, carga los datos, calcula Δt, genera estadísticas descriptivas, crea histogramas, ajusta la exponencial, realiza la prueba KS y produce las imágenes:
```bash
images/histograma_delta_t.png
images/histograma_exponencial.png
```
---
## Estructura del Proyecto
![```tree](tree.png)

## Generar la documentación localmente
```bash
uv run mkdocs serve
```
Luego abrir en el navegador: 
```bash
http://localhost:8000
```
