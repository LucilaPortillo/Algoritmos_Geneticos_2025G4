-----------------------------------------------------------------------------------------------------
												CONCLUSIONES
-----------------------------------------------------------------------------------------------------												
% ¿Por qué conviene hacer un algoritmo genético con lógica y programación?

# Algoritmos Genéticos (AG)

Los algoritmos genéticos son métodos inspirados en un proceso de selección natural que imita la evolución biológica que se utilizan para resolver problemas de optimización y búsqueda. Estos algoritmos funcionan iterativamente, modificanto una población de soluciones candidatas, a través de operadores genéticos como la selección, cruce y mutación.
En cada paso, el algoritmo genético selecciona individuos de la población actual aleatoriamente y
los utiliza como padres para producir los hijos de la siguiente generación.


Conceptos clave:

Población:
Un conjunto de posibles soluciones al problema. 

Individuos (Cromosomas):
Cada solución dentro de la población, representada por un conjunto de genes o características. 

Función de aptitud (Fitness):
Evalúa la calidad de cada individuo (solución) y determina cuán cerca está de la solución óptima.

Operadores Genéticos:
-Selección: Elige individuos de la población actual para reproducirse, basándose en su aptitud (los individuos más aptos tienen más posibilidades de ser seleccionados). 
-Cruce (crossover): Combina los genes de dos individuos seleccionados para crear nuevos individuos (híbridos) con características de ambos. Hay múltiples tipos de cruces, como: Cruce de un punto, Cruce de múltiples puntos, Cruce uniforme, Cruce basado en aritmética (en codificación real)
-Mutación: Introduce cambios aleatorios en los genes de un individuo, lo que ayuda a explorar nuevas regiones del espacio de búsqueda. 

Criterio de parada:
Define cuándo el algoritmo debe detenerse, por ejemplo, cuando se alcanza un número máximo de iteraciones o cuando la mejora en la solución es mínima. 


Funcionamiento:
Inicialización: Se crea una población inicial de individuos aleatorios. 
Evaluación: Se calcula la aptitud de cada individuo en la población usando la función de aptitud. 
Selección: Se seleccionan los individuos más aptos para la reproducción. 
Cruce: Se aplican operadores de cruce a los individuos seleccionados para crear nuevos individuos (descendencia). 
Mutación: Se introduce mutación en algunos individuos de la nueva generación. 
Reemplazo: Se reemplazan algunos individuos de la población antigua por los nuevos individuos generados (descendencia). 
Repetición: Se repiten los pasos 2-6 hasta que se cumpla el criterio de parada. 

En resumen, los algoritmos genéticos utilizan la selección natural para guiar la búsqueda de soluciones óptimas, iterativamente mejorando la población de soluciones a través de la combinación y variación de sus características. 