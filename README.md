# Optimización I: Descenso por Gradiente en Modelo Tipo Gabor 1D

Este repositorio contiene la implementación, análisis y experimentación del algoritmo de **Descenso por Gradiente de paso fijo** aplicado a un modelo no lineal de tipo Gabor 1D. El objetivo principal es observar visualmente el impacto de los hiperparámetros (punto de inicio y tasa de aprendizaje) en la convergencia del modelo.

---

## 🏛️ Información Institucional

* **Institución:** Centro de Investigación y Estudios Avanzados del IPN (Cinvestav) - Unidad Guadalajara
* **Módulo:** Módulo 4: Deep Learning (Actividad en clase)
* **Profesor:** Dr. German Alonso Pinedo Díaz
* **Alumno:** César Geovanni Machuca Pereida

---

## 📝 Descripción del Proyecto

El proyecto consiste en un entorno interactivo desarrollado en un Jupyter Notebook (`.ipynb`) enfocado en la **Optimización**. Mediante la generación de datos sintéticos con ruido aleatorio, se busca ajustar un modelo matemático complejo basado en una función de Gabor unidimensional.

### El Modelo Matemático
El modelo está gobernado por la siguiente ecuación no lineal:

$$y(x) = \sin(z) \exp(-z^2 / 8)$$

Donde la variable latente $z$ depende linealmente de los parámetros óptimos a describir ($\phi_0$ y $\phi_1$):

$$z = \phi_0 + 0.06 \phi_1 x$$

### Regla de Actualización
Para minimizar la función de pérdida del Error Cuadrático Medio (MSE), el algoritmo aplica iterativamente la regla del descenso por gradiente:

$$\phi_{t+1} = \phi_t - \alpha \nabla_\phi L(\phi_t)$$

Donde $\alpha$ representa el *Learning Rate* (tasa de aprendizaje).

---

## 🚀 Estructura del Código y Desarrollo

El código fuente se divide en las siguientes etapas clave:

1. **Generación de Datos Sintéticos:** Creación de una señal limpia con los parámetros verdaderos ($\phi_0 = 3.0, \phi_1 = 15.0$) a la que se le añade ruido Gaussiano.
2. **Cálculo Analítico de Gradientes:** Implementación de las derivadas parciales de la función de pérdida respecto a $\phi_0$ (fase) y $\phi_1$ (frecuencia).
3. **Ciclo de Optimización (El core del ejercicio):** Bloque donde se configuran los valores iniciales y la tasa de aprendizaje (`lr`) para calcular la trayectoria de los parámetros a lo largo de las iteraciones.
4. **Visualización Animada:** Renderizado bidimensional usando `matplotlib.animation` que muestra simultáneamente:
   * **Panel Izquierdo:** La superficie de pérdida $L(\phi_0, \phi_1)$ en curvas de nivel y el camino que recorren los parámetros hacia el mínimo global.
   * **Panel Derecho:** El ajuste en tiempo real de la curva del modelo respecto a los datos dispersos reales.

---

## 🛠️ Requisitos e Instalación

Para ejecutar este notebook de forma local o en entornos en la nube como **Google Colab**, asegúrate de contar con Python 3.10+ y las siguientes dependencias:

```bash
pip install numpy matplotlib ipython
