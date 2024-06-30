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
- **¿Cómo medimos el perfil de sobreendeudamiento de los clientes?**\
Actualmente la entidad financiera mide el perfil de sobreendeudamiento de los clientes a partir de una métrica obsoleta y con datos de los clientes desactualizados lo que no permite medir un perfil con mayor precisión. 

- **¿Cuál es el impacto en los costos de la entidad financiera si se mide incorrectamente el perfil de sobreendeudamiento de los clientes?**\
La baja precisión en la medición del perfil de sobreendeudamiento le ha generado a la entidad financiera un constante crecimiento en su tasa de migración y en sus gastos de provisión. Pues, en los últimos años la entidad financiera ha agregado en su cartera a clientes con perfiles de sobreendeudamiento imprecisos que posteriormente no cumplieron con pagar puntualmente sus créditos reduciendo su nivel esperado de ganancias e incrementando sus costos, así como ha generado que la entidad financiera derive mayores gastos en provisión que como consecuencia le reducen de liquidez para futuros créditos.

- **¿Por qué los clientes migran de no sobreendeudado a potencialmente sobreendeudado/sobreendeudado?**\
En la práctica existen muchos factores que inducen a los clientes a migrar a un perfil sobreendeudado como factores externos a la entidad financiera (desempleo, recesión, pandemia, etc.). Asimismo, existen otros factores que dependen de las acciones directas de la entidad, tales como, topes en las líneas de crédito, cobranzas poco exhaustivas, facilidades de pago, etc. 


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
- **¿Qué información adicional necesitas del departamento de análisis de riesgo para mejorar la identificación de clientes sobreendeudados?**\
Necesitamos datos históricos detallados sobre clientes que han incumplido pagos en el pasado, incluyendo patrones de comportamiento de pago, información sobre créditos anteriores y cualquier indicador temprano de riesgo de sobreendeudamiento.

- **¿Qué recursos necesitas del departamento de TI para implementar y mantener el modelo de machine learning (ML)?**\
Necesitamos acceso a bases de datos actualizadas y capacidades de almacenamiento adecuadas para manejar grandes volúmenes de datos. Además, requerimos soporte técnico para la integración del modelo ML en los sistemas existentes y la implementación de medidas de seguridad de datos.

- **¿El equipo legal necesita revisar las políticas de privacidad y uso de datos en el modelo de ML?**\
Sí, el equipo legal debe revisar y garantizar que el modelo de ML cumpla con todas las regulaciones de privacidad de datos y normativas internas de la empresa. Esto incluye la protección adecuada de la información sensible de los clientes.

- **¿Están de acuerdo en implementar límites a las líneas de crédito y ofrecer créditos con garantías?**\
Es crucial obtener el respaldo del equipo de producto para introducir límites a las líneas de crédito y ofrecer opciones de crédito con garantías, lo cual puede mitigar el riesgo financiero asociado con clientes sobreendeudados.

- **¿Cuál es el cronograma estimado para la implementación del nuevo sistema de evaluación del perfil crediticio?**\
El cronograma debe incluir etapas específicas de desarrollo, pruebas piloto y la implementación completa del nuevo sistema. Se necesita coordinación con TI y otros departamentos clave para garantizar una implementación sin problemas.

- **¿Cuándo se planifica la fase de prueba y cuándo se lanzará oficialmente la campaña de nuevos créditos bajo estas políticas?**\
La fase de prueba debe comenzar una vez que el modelo de ML esté validado y los procesos internos estén listos. El lanzamiento oficial debe estar programado después de completar con éxito las pruebas y obtener la aprobación de todos los departamentos involucrados.

- **¿El equipo de marketing ha desarrollado estrategias para comunicar los cambios en las políticas de crédito a los clientes actuales y potenciales?**\
El equipo de marketing debe desarrollar estrategias claras para comunicar los beneficios y cambios en las políticas de crédito a los clientes, destacando cómo estas mejoras pueden beneficiar su situación financiera y fortalecer la relación con la entidad financiera.

- **¿Hay campañas de educación financiera para ayudar a los clientes a entender las nuevas condiciones y cómo pueden beneficiarse de mejores prácticas de gestión crediticia?**\
Se deben desarrollar campañas educativas para informar a los clientes sobre las nuevas condiciones de crédito, cómo pueden mejorar su perfil crediticio y las mejores prácticas para evitar el sobreendeudamiento, promoviendo así una relación más saludable y duradera.

