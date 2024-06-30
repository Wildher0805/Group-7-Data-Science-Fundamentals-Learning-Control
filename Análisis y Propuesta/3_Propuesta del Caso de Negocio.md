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

## **Framework**
### **¿Qué?**

### **¿Entonces qué?**
- **¿Cómo se utilizará la clasificación de los clientes?**\
La clasificación de clientes según su riesgo de migración de no sobreendeudado a sobreendeudado permite al banco gestionar proactivamente el riesgo crediticio, personalizar las interacciones con los clientes y mejorar la rentabilidad de la cartera crediticia al reducir las pérdidas asociadas con clientes que podrían enfrentar dificultades financieras en el futuro.\

- **¿Cómo se identificarán a los clientes con potencial de sobreendeudamiento?**\
Utilizaremos modelos de machine learning que analicen el historial crediticio, comportamiento de pago y otros factores relevantes para predecir el riesgo de sobreendeudamiento.

- **¿Qué criterios se utilizarán para clasificar a los clientes en riesgo de sobreendeudamiento?**\
Se considerarán variables como nivel de ingresos, deudas actuales, historial crediticio, comportamiento de pago y otros indicadores financieros para determinar la clasificación de riesgo.

- **¿Cómo se utilizará esta clasificación para reducir el costo de provisión en el banco?**\
Al identificar a los clientes con potencial de sobreendeudamiento, podremos tomar medidas preventivas como ajustar límites de crédito, ofrecer asesoramiento financiero o reestructurar deudas, lo que ayudará a reducir el riesgo de impago y, por ende, el costo de provisión.

- **¿Qué acciones se tomarán una vez identificados los clientes en riesgo de sobreendeudamiento?**\
Se implementarán estrategias personalizadas para cada cliente identificado, como ofrecer productos financieros más adecuados a su perfil, establecer planes de pago flexibles o brindar educación financiera para mejorar su situación.

- **¿Cómo se medirá el impacto de esta estrategia en la reducción del costo de provisión?**\
Se realizará un seguimiento continuo de los clientes clasificados como riesgosos para evaluar su comportamiento financiero, comparando los resultados con un grupo de control, y así determinar el impacto real de la estrategia en la reducción del costo de provisión del banco.

### **¿Y ahora qué?**

