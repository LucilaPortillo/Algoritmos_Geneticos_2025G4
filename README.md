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
% Individuos como listas de 0s y 1s
individuo([1,0,1,0]).
individuo([0,1,1,1]).
individuo([1,1,0,1]).

% Cuenta los unos en la lista (fitness)
fitness([], 0).
fitness([1|T], F) :- fitness(T, F1), F is F1 + 1.
fitness([0|T], F) :- fitness(T, F).

% Ejemplo:
% ?- fitness([1,0,1,1], F).
% F = 3.

% Selección (por torneo simple entre dos)
% Selecciona el mejor entre dos individuos
seleccion(I1, I2, Mejor) :-
    fitness(I1, F1),
    fitness(I2, F2),
    (F1 >= F2 -> Mejor = I1 ; Mejor = I2).

% Cruce (punto fijo en la mitad)
% Corta una lista a la mitad
dividir(Lista, L1, L2) :-
    length(Lista, N),
    Half is N // 2,
    length(L1, Half),
    append(L1, L2, Lista).

% Cruce de dos individuos
cruzar(P1, P2, Hijo) :-
    dividir(P1, A1, _),
    dividir(P2, _, A2),
    append(A1, A2, Hijo).

% Mutación (cambia un bit aleatoriamente)
mutar_bit(0, 1).
mutar_bit(1, 0).

% Mutar una lista: muta un solo bit aleatoriamente
mutar([], []).
mutar([H|T], [Hmut|T]) :-
    random(0.0, 1.0, R),
    (R < 0.25 -> mutar_bit(H, Hmut) ; Hmut = H).

% Crear un hijo con cruce y mutación
reproducir(P1, P2, HijoMutado) :-
    cruzar(P1, P2, Hijo),
    mutar(Hijo, HijoMutado).

```



-----------------------------------------------------------------------------------------------------
				                    CONCLUSIONES
-----------------------------------------------------------------------------------------------------												