# Soluciones_Analiticas_Numericas
cat << 'EOF' > README.md
# Comparación de Soluciones Analíticas y Numéricas (Método de Euler)

Este repositorio contiene un código en Python que resuelve una ecuación diferencial ordinaria (EDO) separable de manera analítica y la compara con su aproximación numérica mediante el **Método de Euler** en el intervalo $t \in [0, 1]$ con un paso $h = 0.2$[cite: 8].

## 1. Problema Seleccionado

Se eligió la ecuación diferencial separable con condición inicial:

$$\frac{dy}{dt} = 2ty, \quad y(0) = 1$$

## 2. Solución Analítica (Separación de Variables)

1. Separamos variables:
   $$\frac{1}{y}\,dy = 2t\,dt$$

2. Integramos ambos lados:
   $$\int \frac{1}{y}\,dy = \int 2t\,dt \implies \ln|y| = t^2 + C$$

3. Despejamos $y(t)$:
   $$y(t) = C_1 e^{t^2}$$

4. Aplicamos la condición inicial $y(0) = 1$:
   $$1 = C_1 e^{0} \implies C_1 = 1$$

La **solución exacta** es:

$$y(t) = e^{t^2}$$

## 3. Método de Euler ($t \in [0, 1]$, $h = 0.2$)

La fórmula iterativa del método de Euler es:

$$y_{n+1} = y_n + h \cdot f(t_n, y_n)$$

Con $f(t, y) = 2ty$, $t_0 = 0$, $y_0 = 1$ y $h = 0.2$:

| $t$ | Solución Exacta $e^{t^2}$ | Aproximación Euler ($h=0.2$) | Error Absoluto |
| :-: | :-: | :-: | :-: |
| 0.0 | 1.000000 | 1.000000 | 0.000000 |
| 0.2 | 1.040811 | 1.000000 | 0.040811 |
| 0.4 | 1.173511 | 1.080000 | 0.093511 |
| 0.6 | 1.433329 | 1.252800 | 0.180529 |
| 0.8 | 1.896481 | 1.553472 | 0.343009 |
| 1.0 | 2.718282 | 2.050583 | 0.667699 |

## 4. Conclusión

El método de Euler captura el crecimiento de la solución, pero presenta un error creciente al usar $h = 0.2$ debido a la rápida aceleración de la pendiente $2ty$. Disminuir el tamaño de paso $h$ mejora la precisión numérica.
EOF
