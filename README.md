# TFG-Estad-stica-Bayesiana
Códigos usados para el trabajo de fin de grado de Javier González Moreno.
import numpy as np
import matplotlib.pyplot as plt

# Generar puntos aleatorios
np.random.seed(0)
n_points = 10000
x = np.random.uniform(-1, 1, n_points)
y = np.random.uniform(-1, 1, n_points)

# Calcular distancias desde el origen
distances = np.sqrt(x**2 + y**2)
inside_circle = distances <= 1

# Estimación de pi
pi_estimate = 4 * np.sum(inside_circle) / n_points

# Gráfico
plt.figure(figsize=(8, 8))
plt.scatter(x[inside_circle], y[inside_circle], color='blue', s=1, label='Dentro del Círculo')
plt.scatter(x[~inside_circle], y[~inside_circle], color='red', s=1, label='Fuera del Círculo')
plt.xlabel('x',fontsize=16)
plt.ylabel('y', fontsize=16)
plt.title(f'Estimación de Pi con Método de Monte Carlo: {pi_estimate:.4f}',fontsize=20)
plt.legend()
plt.grid(False)
plt.axis('equal')
plt.show()
