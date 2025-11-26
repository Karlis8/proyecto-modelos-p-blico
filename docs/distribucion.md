# Distribución Exponencial del Modelo

En este documento se describe el modelo teórico utilizado para analizar los intervalos de tiempo entre eventos (`Δt`). Se muestra la función de densidad, la estimación del parámetro y la propiedad fundamental de la distribución: memoria nula.

---

## Modelo propuesto

Los tiempos entre eventos se modelan mediante una **distribución exponencial**, común en procesos donde los eventos ocurren de manera aleatoria pero con una tasa constante.

La función de densidad de probabilidad (PDF) es:

\[
f(x) = \lambda e^{-\lambda x}, \qquad x \ge 0
\]

donde:

- \( x \) es el tiempo entre eventos,
- \( \lambda \) es la tasa de eventos por segundo.

---

## Función de distribución acumulada (CDF)

La probabilidad de que el intervalo sea menor o igual a un valor \( x \) viene dada por:

\[
F(x) = 1 - e^{-\lambda x}
\]

---

## Estimación del parámetro λ

El mejor estimador por máxima verosimilitud para datos exponenciales es:

\[
\hat{\lambda} = \frac{1}{\bar{x}}
\]

En este proyecto, con una media muestral de:

\[
\bar{x} = 25.24475 \text{ s}
\]

el valor estimado fue:

\[
\hat{\lambda} = 0.03961
\]

Este parámetro es el que se usó para generar la curva teórica del histograma ajustado.

---

## Propiedad de memoria nula

Una característica fundamental de la distribución exponencial es la **propiedad de falta de memoria**, que establece que:

\[
P(X > t + s \mid X > s) = P(X > t)
\]

Esta ecuación indica que:

- El tiempo que ya ha transcurrido no afecta la probabilidad del tiempo restante.
- El proceso “vuelve a empezar” siempre.
- Es una característica exclusiva de la distribución exponencial.

Esto es consistente con un **proceso de Poisson**, donde los eventos son independientes y ocurren con una tasa constante.

---

## Interpretación en el contexto del proyecto

El cumplimiento de esta propiedad (junto con la prueba de Kolmogorov–Smirnov y el ajuste visual) respalda que los datos del sensor se comportan como un proceso de llegadas aleatorio con tasa constante.  

Por ello, el modelo exponencial es adecuado para describir los intervalos temporales observados.
