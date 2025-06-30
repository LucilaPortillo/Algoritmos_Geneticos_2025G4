# Algoritmos Genéticos (AG)

Los algoritmos genéticos son una clase particular de algoritmos evolutivos (*Evolutionary Algorithms, EA*) y estos son una familia de algoritmos de optimización y búsqueda basados en la evolución biologica.

Los algoritmos genéticos funcionan iterativamente, modificanto una población de soluciones candidatas, a través de **operadores genéticos** como la **selección**, **cruce** y **mutación**.  
En cada paso, el algoritmo genético selecciona individuos de la población actual aleatoriamente y los utiliza como padres y simula la reproduccion para producir los hijos de la siguiente generación producto de la combinación y variación de sus características.  
En vez de una sola población, puede haber dos o más poblaciones que co-evolucionan, por ejemplo **depredadores y presas**.

---

## Conceptos clave

---

#### **Población**
Un conjunto de posibles soluciones al problema. 

#### **Individuos (Cromosomas)**
Cada solución dentro de la población, representada por un conjunto de genes o características. 

#### **Función de aptitud (Fitness)**
Evalúa la calidad de cada individuo (solución) y determina cuán cerca está de la solución óptima.

---

#### **Operadores Genéticos**

- **Selección**:  
  Elige individuos de la población actual para reproducirse, basándose en su aptitud (los individuos más aptos tienen más posibilidades de ser seleccionados). 

- **Cruce (crossover) o Reproduccion**:  
  Combina los genes de dos individuos seleccionados para crear nuevos individuos (híbridos) con características de ambos.  
  Hay múltiples tipos de cruces, como:  
  - *Cruce de un punto*: se elige un punto de cruce en los cromosomas de los padres y se intercambian las porciones de los cromosomas  
  - *Cruce de dos puntos*: se eligen dos puntos de cruce y se intercambian las secciones internas entre los puntos  
  - *Cruce uniforme*: cada gen del hijo se toma aleatoriamente de uno de los dos padres

- **Mutación**:  
  Introduce cambios aleatorios en los genes de un individuo, lo que ayuda a explorar nuevas regiones del espacio de búsqueda.  
  - *Mutación puntual*: un gen en el cromosoma es alterado  
  - *Mutación por intercambio*: dos genes en el cromosoma son intercambiados  
  - *Mutación por inversión*: una subsección del cromosoma es invertida

---

### **Reemplazo**

Se refiere a cómo se introduce la nueva generación en la población, sustituyendo a los individuos previos.  
Los subtipos incluyen:

- Reemplazo generacional: toda la población es reemplazada por la nueva generación  
- Reemplazo por torneos: parte de la población es reemplazada mediante torneos entre individuos viejos y nuevos  
- Reemplazo elitista: algunos de los mejores individuos de la generación anterior se mantienen en la nueva generación para asegurar la calidad de las soluciones  
- Reemplazo de padres: los individuos que fueron seleccionados como padres son reemplazados en la nueva generación  
- Reemplazo de individuos similares: los nuevos individuos reemplazan a los más similares genéticamente de la generación anterior para mantener la diversidad  
- Reemplazo de peores individuos: los individuos menos aptos de la generación anterior son reemplazados por los nuevos individuos  
- Reemplazo aleatorio: algunos individuos de la generación anterior son reemplazados aleatoriamente por nuevos individuos

---

### **Criterio de parada**

Define cuándo el algoritmo debe detenerse, por ejemplo:

- Cuando se alcanza un número máximo de iteraciones  
- Cuando la mejora en la solución es mínima  

---

## Funcionamiento

1. **Inicialización**: Se crea una población inicial de individuos aleatorios.  
2. **Evaluación**: Se calcula la aptitud de cada individuo en la población usando la función de aptitud.  
3. **Selección**: Se seleccionan los individuos más aptos para la reproducción.  
4. **Cruce o reproducción**: Se aplican operadores de cruce a los individuos seleccionados para crear nuevos individuos (descendencia).  
5. **Mutación**: Se introduce mutación en algunos individuos de la nueva generación.  
6. **Reemplazo**: Se introduce la nueva generación en la población, sustituyendo individuos de la población antigua por los nuevos individuos generados (descendencia).  
7. **Convergencia**: Se repiten los pasos 2-6 hasta que se cumpla el criterio de parada.  

---

A veces los algoritmos genéticos no se usan para resolver el problema directamente, sino para encontrar o ajustar otros algoritmos o arquitecturas de redes neuronales.

---

## Entrenamiento de redes neuronales con algoritmos evolutivos

Tradicionalmente, las redes neuronales se entrenan con gradiente descendente y *backpropagation*. Sin embargo, también se pueden entrenar usando algoritmos evolutivos, especialmente cuando:

- No se dispone del gradiente (por ejemplo, en entornos no diferenciables).  
- Hay múltiples objetivos o ruido en el entorno.  
- Se quiere evitar mínimos locales (los EA exploran mejor el espacio de soluciones).  

Esto se conoce como **neuroevolución**.

---

### ¿Cómo funciona?

- **Genotipo (cromosoma)**: es un vector que representa todos los pesos y sesgos de una red neuronal.  
- **Individuo**: una red neuronal completa con una cierta configuración de pesos.  
- **Función de aptitud (fitness)**: mide el rendimiento de esa red (por ejemplo, precisión en un conjunto de validación, puntaje en un juego, etc.).  

Se realiza:

- Selección de las mejores redes.  
- Cruce entre sus pesos.  
- Mutación de algunos pesos.  

Tras varias generaciones, se obtienen redes con muy buen rendimiento.

Ideal cuando:

- No se puede usar derivadas  
- Hay ruido  
- El entorno no es diferenciable (por ejemplo: juegos, simulaciones físicas, control robótico)

---

### Un caso muy conocido es NEAT (Stanley & Miikkulainen, 2002):

- No solo evoluciona los pesos, sino también la topología (estructura) de la red.  
- Empieza con redes simples y va creciendo su complejidad.  
- Usa códigos genéticos especiales, con historiales de innovación, para cruzar redes de distinta forma.  

NEAT se ha usado con éxito en videojuegos, robótica y optimización sin supervisión.

---

## ¿Por qué conviene hacer un algoritmo genético con lógica y programación?

Implementar un algoritmo genético con lógica y programación conviene porque el funcionamiento mismo de estos algoritmos se basa en principios lógicos aplicados paso a paso.  
Los operadores genéticos (recombinación y mutación) combinan y modifican soluciones existentes usando principios lógicos, esta combinación responde a una lógica estructurada: cruzar genes compatibles, variar componentes de forma puntual y mantener la validez de las soluciones.  

La función de aptitud utiliza lógica para evaluar la calidad de las soluciones, evalúa cada individuo en función de un conjunto de reglas o condiciones definidas previamente.  

El proceso de selección se basa en principios lógicos de selección natural. Puede entenderse como una consecuencia lógica del principio de aptitud: se seleccionan aquellos individuos que cumplen con las condiciones deseadas.  

El criterio de parada se define lógicamente para determinar cuándo detener el algoritmo.

---

## Ejemplo en Prolog

```prolog
% Población inicial
poblacion_inicial([34, 87, 12, 63]). 

% Evaluar aptitud (más cerca de 100 es mejor)
evaluar(X, Aptitud) :-
    Distancia is abs(100 - X),
    Aptitud is 100 - Distancia.


% Seleccionar los dos mejores
seleccionar_mejores(Poblacion, Mejor1, Mejor2) :-
    map_list_to_pairs(evaluar, Poblacion, Pares),
    keysort(Pares, Ordenados),
    reverse(Ordenados, [_-Mejor1, _-Mejor2 | _]).

% Cruce (promedio entre dos padres)
cruzar(PadreX, PadreY, Hijo) :-
    H is (PadreX + PadreY) // 2,
    Hijo = H.

% Mutación (sumar o restar un valor aleatorio pequeño)
mutar(Hijo, Mutado) :-
    random_between(-10, 10, ValorAleatorio),
    writeln('Función mutar: '),
    write('Valor sumado a mutado: '), writeln(ValorAleatorio),
    writeln('------------------------------------'),
    Mutado is Hijo + ValorAleatorio.

% Evolucionar una generación
evolucionar(PoblacionActual, NuevaPoblacion) :-
    seleccionar_mejores(PoblacionActual, Mutacion1, Mutacion2),
    cruzar(Mutacion1, Mutacion2, Hijo1), mutar(Hijo1, M1Mutado),
    cruzar(Mutacion2, Mutacion1, Hijo2), mutar(Hijo2, M2Mutado),
    NuevaPoblacion = [Mutacion1, Mutacion2, M1Mutado, M2Mutado].


% Correr:
%     	poblacion_inicial(PrimeraGeneracion), 
%    	evolucionar(PrimeraGeneracion, SegundaGeneracion),
%		seleccionar_mejores(SegundaGeneracion, Mejor, _), 	
%    	evaluar(Mejor, AptitudDelMejor).
```



-----------------------------------------------------------------------------------------------------
				                    CONCLUSIONES
-----------------------------------------------------------------------------------------------------												