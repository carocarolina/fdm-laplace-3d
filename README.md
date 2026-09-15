# 3D Laplace Equation Solver: FDM vs. Analytical Series

Este proyecto resuelve la ecuación de Laplace en 3D ($\nabla^2 V = 0$) aplicando el Método de Diferencias Finitas (FDM) y valida los resultados contra la solución analítica exacta mediante series de Fourier.

## Herramientas Usadas
- **Python 3**
- **SciPy** (`scipy.sparse` para matrices dispersas, `spla.bicgstab` para solvers iterativos)
- **NumPy** (vectorización y manejo de arrays n-dimensionales)
- **Matplotlib & Pandas** (visualización y tablas de rendimiento)

## Desafíos Técnicos y Optimizaciones
- **Eficiencia de Memoria RAM:** Se optimizó la construcción de la matriz de coeficientes en formato disperso CSR sin pasar por representaciones densas ni intermediarios ineficientes (`LIL`), reduciendo el uso de RAM de decenas de GB a menos de 100 MB para $343.000$ nodos ($70 \times 70 \times 70$).
- **Estabilidad Numérica:** Se utilizó una formulación basada en $\sinh$ para prevenir errores de desbordamiento numérico (*overflow*) en el cálculo de la serie de Fourier.

## Resultados y Conclusión
El modelo demuestra una convergencia de orden $O(h^2)$ al reducir el paso de malla $h$, verificando la exactitud del algoritmo frente a la solución analítica teórica.
