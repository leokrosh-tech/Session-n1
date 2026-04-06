# Reporte de Laboratorio: Implementación de Transfer Learning
**Sesión 5** | **Estudiante:** Leonel Crespo

---

## 1. Concepto de Transfer Learning
Desde mi perspectiva, el **Transfer Learning** consiste en la reutilización de conocimiento previamente adquirido por una red neuronal. En lugar de iniciar un entrenamiento desde cero —lo cual implicaría que la IA aprenda a identificar elementos primarios como bordes o contrastes—, empleamos un modelo "pre-entrenado" que ya domina estas bases. 

De este modo, solo ajustamos las capas finales para especializarlo en nuestra tarea, optimizando radicalmente los tiempos de cómputo y los recursos de hardware.

## 2. Arquitectura Seleccionada: MobileNetV2
Para esta práctica se optó por **MobileNetV2**, un modelo que destaca por los siguientes pilares:

* **Optimización para Móviles:** Su arquitectura está refinada para ejecutarse en entornos con hardware limitado o memoria restringida.
* **Eficiencia Estructural:** Utiliza bloques residenciales invertidos (*bottleneck layers*), lo que permite una inferencia veloz sin sacrificar la precisión del reconocimiento.
* **Conocimiento Base:** El modelo llega con una "sabiduría" previa obtenida del dataset **ImageNet**, permitiéndole identificar una vasta gama de patrones visuales.

## 3. Análisis de Resultados (Predicción)
Durante la fase de pruebas, se validó el rendimiento del modelo con los siguientes datos:

* **Entrada de datos:** Fotografía de un espécimen de *Golden Retriever*.
* **Resultado de Clasificación:** El sistema arrojó una coincidencia con la clase "Golden Retriever" alcanzando un **95% de fiabilidad**.
* **Validación:** El resultado fue exitoso. Esto confirma que el modelo es capaz de transferir sus capacidades generales a casos específicos de manera efectiva.

## 4. Distribución de Parámetros del Modelo
Tras la configuración de las capas y la aplicación de técnicas de *fine-tuning*, el balance de parámetros se dividió de la siguiente manera:

| Tipo de Parámetro | Cantidad Aproximada | Función |
| :--- | :--- | :--- |
| **Totales** | 2,257,984 | Suma completa de la capacidad de la red. |
| **Congelados** | 2,223,872 | Capas de extracción de características básicas (pesos fijos). |
| **Entrenables** | 34,112 | Capas densas finales ajustadas para la tarea específica. |

## 5. Propuesta de Aplicación Regional
Como se planteó en la Actividad A1, una aplicación de alto impacto sería la **detección temprana de patologías en cultivos de papa en el altiplano de Bolivia**. 

Gracias al Transfer Learning, no es necesario recolectar millones de imágenes; con un set de datos reducido de hojas afectadas, podemos especializar la parte final de MobileNetV2 para generar una herramienta de diagnóstico agrícola accesible y eficiente.

## 6. Conclusiones y Observaciones
Lo que más resalto de este ejercicio es la versatilidad de los modelos ligeros. Es impresionante cómo un sistema tan compacto posee una capacidad de análisis tan robusta. La técnica de bloquear y desbloquear capas (**freezing**) otorga un control total sobre el aprendizaje del modelo, permitiendo reconvertir una herramienta de propósito general en una solución específica en cuestión de minutos.
