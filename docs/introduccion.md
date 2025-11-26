# Introducción

El presente proyecto tiene como objetivo analizar el comportamiento temporal de un conjunto de mediciones tomadas desde un sensor físico. En particular, se estudia la diferencia de tiempo entre muestras consecutivas (Δt), con el fin de determinar si dichas variaciones siguen un patrón aleatorio característico de un proceso de Poisson.

Este tipo de análisis es relevante para sistemas en los que:

- La llegada de eventos es aleatoria.
- El muestreo no ocurre en intervalos fijos.
- Se desea detectar fallos, retardos o comportamientos anómalos en la captura de datos.
- Se requiere caracterizar estadísticamente la ocurrencia de eventos independientes.

Para ello se desarrolló un sistema de adquisición que registra cada medición en una base de datos SQLite. A partir de ese registro se aplicó un proceso de análisis estadístico en Python, orientado a verificar si los valores Δt pueden modelarse mediante una distribución exponencial.

La documentación presenta tanto el procedimiento seguido como los resultados obtenidos y la interpretación final.
