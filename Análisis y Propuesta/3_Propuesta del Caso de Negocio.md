# **PROPUESTA DEL CASO DE NEGOCIO**
## **SOLUCIÓN DE MACHINE LEARNING: Decision Tree**

### Concepto de Árbol de Decisión

Un Árbol de Decisión es un modelo de predicción utilizado tanto para problemas de clasificación como de regresión. Se basa en dividir repetidamente el espacio de características en subconjuntos más homogéneos, de acuerdo con una serie de reglas de decisión que se derivan de los datos de entrenamiento. Cada nodo interno del árbol representa una prueba en una característica, cada rama representa el resultado de la prueba, y cada hoja representa una predicción de etiqueta o valor.

### Funcionamiento de un Árbol de Decisión

1. **Selección de la característica y punto de corte**:
    - Para cada nodo del árbol, se elige la característica y el punto de corte que mejor separen los datos en términos de una medida de pureza, como la **impureza de Gini** o la **entropía** (para clasificación) o el **error cuadrático medio** (para regresión).

    $$
    \text{Impureza de Gini:} \quad G = 1 - \sum_{i=1}^{C} p_i^2
    $$

    $$
    \text{Entropía:} \quad H = - \sum_{i=1}^{C} p_i \log(p_i)
    $$

    Donde \( p_i \) es la proporción de ejemplos de clase \( i \) en el nodo.

2. **División del nodo**:
    - Los datos se dividen en dos subconjuntos según la característica y el punto de corte seleccionados. Esta división se realiza de manera recursiva, creando ramas y nodos hijos hasta que se cumpla un criterio de parada.

3. **Criterios de parada**:
    - Algunos de los criterios de parada comunes son:
        - Alcanzar una profundidad máxima del árbol.
        - Tener un número mínimo de muestras en un nodo.
        - No obtener una mejora significativa en la medida de pureza.

4. **Asignación de una predicción a cada hoja**:
    - Una vez que se alcanzan las hojas del árbol, se asigna una predicción a cada una de ellas:
        - **Para clasificación**: La clase más frecuente entre las muestras en la hoja.

        $$
        \hat{y} = \text{mode}(y_1, y_2, \ldots, y_n)
        $$

        - **Para regresión**: El promedio de los valores de las muestras en la hoja.

        $$
        \hat{y} = \frac{1}{n} \sum_{i=1}^{n} y_i
        $$

### Ventajas

- **Interpretabilidad**: Los árboles de decisión son fáciles de entender y visualizar.
- **Manejo de datos categóricos y numéricos**: Pueden manejar ambos tipos de datos sin necesidad de preprocesamiento excesivo.
- **Poca necesidad de normalización de datos**: No requieren que las características estén en la misma escala.

### Desventajas

- **Propensión al sobreajuste**: Los árboles de decisión pueden crear modelos muy complejos que se ajustan demasiado a los datos de entrenamiento.
- **Inestabilidad**: Pequeñas variaciones en los datos pueden llevar a la creación de árboles de decisión muy diferentes.

En resumen, los árboles de decisión son una herramienta poderosa y flexible para realizar predicciones, pero es importante controlar su complejidad para evitar problemas de sobreajuste.
