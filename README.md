# TP4: Aprendizaje No Supervisado

Este repositorio contiene la resolución del Trabajo Práctico N° 4 de la asignatura Sistemas de Inteligencia Artificial. Se implementan y analizan tres modelos de aprendizaje no supervisado: Redes de Kohonen (SOM), Regla de Oja y Redes de Hopfield.

## Estructura del Proyecto

- `europe.csv`: Conjunto de datos con características socioeconómicas de 28 países europeos.
- `TP4_Kohonen.ipynb`: Implementación de una Red de Kohonen (Self-Organizing Map) para el clustering de países.
- `TP4_Oja.ipynb`: Implementación de la Regla de Oja para el cálculo de la primera componente principal (PCA).
- `TP4_Hopfield.ipynb`: Implementación de una Red de Hopfield para memoria asociativa y reconocimiento de patrones.

---

## 1. Ejercicio Europa

### 1.1 Red de Kohonen (SOM)
Se implementó un mapa auto-organizado para agrupar países europeos según sus similitudes geopolíticas y económicas (PBI, inflación, desempleo, etc.).

**Características principales:**
- Grilla de neuronas con pesos inicializados aleatoriamente.
- Entrenamiento competitivo encontrando la BMU (*Best Matching Unit*).
- Visualización de la **U-Matrix** para analizar distancias promedio entre neuronas vecinas.
- Mapa de asignación de países por neurona.

### 1.2 Regla de Oja
Se implementó un modelo de una sola neurona lineal que utiliza la regla de Oja para extraer el autovector correspondiente a la mayor varianza de los datos (PC1).

**Puntos clave:**
- Normalización de datos (StandardScaler).
- Comparación de los pesos finales con los autovectores obtenidos mediante `sklearn.decomposition.PCA`.
- Gráfico de convergencia del vector de pesos.

---

## 2. Red de Hopfield

Se construyó una red de Hopfield de 25 neuronas para almacenar y recuperar patrones de letras en una grilla de 5x5.

### Tareas realizadas:
- **Almacenamiento:** Se guardaron 4 letras (A, Y, H, Z) utilizando la regla de Hebb.
- **Recuperación con ruido:** Se generaron versiones ruidosas (20% de bits invertidos) y se verificó que la red converge al patrón original. Se muestra el proceso paso a paso de la actualización asíncrona.
- **Estados Espúreos:** Se ingresaron patrones con ruido muy alto (≥50%) para identificar estados espúreos (mínimos locales de energía que no corresponden a patrones almacenados, como los *mixed states*).

---

## Requisitos

- Python 3.x
- NumPy
- Pandas
- Matplotlib
- Scikit-learn (solo para preprocesamiento y validación de PCA)

## Cómo ejecutar

Cada ejercicio se encuentra detallado en su respectivo Jupyter Notebook. Para visualizarlos, ejecute:
```bash
jupyter notebook
```
Y abra los archivos `.ipynb` mencionados arriba.