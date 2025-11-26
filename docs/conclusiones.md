# Conclusiones

El análisis realizado sobre los intervalos de tiempo entre eventos (`Δt`) permitió evaluar el comportamiento estadístico del sistema de adquisición de datos y determinar si sigue un patrón propio de un proceso de Poisson.

---

## Principales hallazgos

1. **Los datos obtenidos fueron consistentes y permitieron calcular 620 intervalos temporales**, suficientes para realizar un análisis confiable.

2. **El histograma de los tiempos entre llegadas mostró una forma claramente decreciente**, tal como se espera en una distribución exponencial.

3. La **estimación por máxima verosimilitud** produjo un valor:

\[
\hat{\lambda} = 0.03961
\]

lo que indica una tasa promedio aproximada de un evento cada **25.24 s**, coherente con la media observada.

4. La **curva teórica exponencial con parámetro \(\hat{\lambda}\)** se ajustó de manera visualmente adecuada al histograma normalizado.

5. La **prueba de bondad de ajuste Kolmogorov–Smirnov (KS)** arrojó:

- Estadístico: \( D = 0.03494 \)  
- P-value: \( p = 0.4259 \)

Con un nivel de significancia del 5%, **no se rechaza la hipótesis de que los datos provienen de una distribución exponencial**.

Esto confirma formalmente que el modelo teórico describe adecuadamente el comportamiento de los tiempos entre eventos.

---

## Interpretación del comportamiento del sistema

Los resultados permiten concluir que:

- El sistema de adquisición genera eventos con **tasa de llegada aproximadamente constante**.  
- Los tiempos entre eventos son **independientes** y presentan **falta de memoria**, propiedad característica de la distribución exponencial.  
- El proceso se aproxima a un **proceso de Poisson**, común en sistemas de medición, sensado o captura de eventos aleatorios.

---

## Limitaciones del estudio

Aunque el ajuste fue satisfactorio, es importante señalar:

- La adquisición se realizó bajo un único conjunto de condiciones; otros escenarios podrían modificar la tasa de llegadas.  
- No se descartó ruido adicional en el hardware o el sistema operativo que pudiera introducir variabilidad no modelada.  
- La validación se basa únicamente en el análisis temporal; no se consideraron características adicionales del sensor o del entorno.

---

## Trabajo futuro recomendado

Para complementar o extender el análisis, se sugieren las siguientes líneas:

- Repetir la adquisición bajo diferentes cargas del sistema o condiciones ambientales.  
- Comparar con otros modelos estadísticos (p. ej., Weibull, Gamma) para evaluar si alguno ofrece un ajuste superior.  
- Realizar análisis de autocorrelación para confirmar aún más la independencia entre eventos.  
- Incorporar técnicas de detección de outliers para evaluar la sensibilidad del modelo.  
- Automatizar el flujo completo: adquisición → almacenamiento → análisis → reporte.

---

## Conclusión final

El estudio demuestra que el comportamiento temporal del sistema de medición puede modelarse adecuadamente mediante una distribución exponencial.  
La evidencia empírica, visual y estadística respalda este resultado, permitiendo afirmar que el proceso temporal sigue una dinámica compatible con un proceso de Poisson.

Este modelo puede utilizarse como base para futuras simulaciones, predicciones o estudios sobre la estabilidad del sistema de adquisición.
