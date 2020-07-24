<!--
.. title: ¿Qué es la Probabilidad?
.. slug: what-is-probability
.. date: 2020-06-26 09:32:29 UTC+02:00
.. tags: 
.. category: 
.. link: 
.. description: 
.. type: text
.. has_math: yes
-->

# Capítulo 0
La palabra "Probabilidad" es familiar, podemos asociarla con cartas o dados, incluso con el destino o la suerte. Creemos que sabemos qué significa la probabilidad, pero si hacemos el ejercicio de intentar definirla, no es una tarea sencilla. Las acepciones que contempla la R.A.E. son las siguientes:

1. Verosimilitud o fundada apariencia de verdad.
2. Cualidad de probable (que se verificará o sucederá).
3. Mat. En un proceso aleatorio, razón entre el número de casos favorables y el número de casos posibles.

La primera acepción relaciona la probabilidad con la verosimilitud, la segunda nos redirige al término "probable", y la tercera, la supuesta definición matemática, la define como el cociente entre número de casos favorables y posibles. 
La tercera acepción es la más conocida, por ejemplo, si decimos que en España 5 de cada 50 millones de personas son rubias, diremos que se tiene un 10% de probabilidad de ser rubio. Esta manera de razonar lleva a creer que la probabilidad de algo se obtiene observando la realidad, pero veremos que la probabilidad es una idea que nosotros definimos, y que, si está bien definida, puede ser útil para modelar algunas situaciones del mundo real.

<!-- # Chapter 0
We all are familiar with the word "probability", we may associate it with cards and dices, or even with fate or luck. We believe that we know what probability means, but if we make the exercise to try to define it, it is no easy task. Looking at some dictionaries we get the following definitions:
> How likely something is to happen
> 
> -- <cite>Oxford Dictionary</cite>

> How likely something is, sometimes calculated in a mathematical way
> 
> -- <cite>Longman Dictionary of Contemporary English Online</cite>

These two definitions link the meaning of probability with that of likelihood, which is just shirking the question. The definitions for likelihood are:
> The chance of something happening
> 
> -- <cite>Oxford Dictionary</cite>

> The degree to which something can reasonably be expected to happen
> 
> -- <cite>Longman Dictionary of Contemporary English Online</cite>

Although these definitions seem intuitive or natural, they are vague and ethereal, they are just not useful to construct a mathematical concept to work with.
One of the definition of probability shown in the Merriam-Webster dictionary is more definite:
> The ratio of the number of outcomes in an exhaustive set of equally likely outcomes that produce a given event to the total number of possible outcomes
> 
> -- <cite>Merriam-Webster</cite>

This could be useful to develop something that we can use.
The most spread mathematical notion of probability is the ratio between positive and total cases of a certain event.  For example, say that 5 out of 50 million people in Spain are blonde. Then, the common assertion would be: "In Spain, you have a 10% probability of being blonde", where 10% = 5/50, that is, number of positive cases divided by the total number of cases.
However, this is actually closer to statistics than to probability. This part is tricky, so for a better understanding we will forget about statistics and we will discuss about probability and, if necessary, inverse probability. -->

## Espacio Muestral y Espacio de Sucesos
Para definir "Probabilidad", es necesario definir el *espacio muestral* $\Omega$ de un experimento aleatorio, así como el espacio de sucesos $\Sigma$. El espacio muestral es el conjunto de todos los posibles resultados de un experimento alreatorio. Veamos algunos ejemplos.

### Ejemplo de la Moneda
Imaginemos que nuestro experimento es lanzar una moneda al aire, entonces el espacio muestral es:
$$ \Omega = \lbrace Cara, Cruz \rbrace = \lbrace C, X \rbrace . $$
El espacio de sucesos es el conjunto de todos los posibles sucesos, y un suceso es cualquier subconjunto del espacio muestral. En nuestro ejemplo, el espacio de sucesos es 
$$ \Sigma = \lbrace \lbrace  \rbrace, \lbrace H \rbrace, \lbrace T \rbrace, \lbrace H, T \rbrace  \rbrace. $$
Aquí $\lbrace  \rbrace$ es el conjunto vacío, que normalmente se denota por $\emptyset$, y $\lbrace H, T \rbrace$ es el conjunto muestral $\Omega$. Estos dos eventos son especiales porque siempre se incluyen en el espacio de sucesos $\Sigma$, sin embargo el significado de estos dos eventos no es muy intuitivo.


<!-- ## Sample Space and Event Space
To define probability, it is necessary to define the *sample space* $\Omega$ of an experiment, and also the *event space* $\Sigma$. The sample space is the set of all possible outcomes of a certain experiment or random trial.

### Coin Example
Imagine that our experiment is the toss of a coin, then the sample space is 
$$ \Omega = \lbrace Head, Tail \rbrace = \lbrace H, T \rbrace . $$ 
The event space is the set of all possible events where an event is any subset of the sample space. In our example, the event space is 
$$ \Sigma = \lbrace \lbrace  \rbrace, \lbrace H \rbrace, \lbrace T \rbrace, \lbrace H, T \rbrace  \rbrace. $$
Here, $\lbrace  \rbrace$ is the empty set, which tipically is denoted as $\emptyset$, and $\lbrace H, T \rbrace$ is the sample space $\Omega$. These two events are special because they are always included in the event space $\Sigma$, however the meaning of these events is not very intuitive. -->

<!-- 
### Coin Example
Imagine that our experiment is the toss of a coin, then the sample space is 
$$ \Omega = \lbrace Head, Tail \rbrace = \lbrace H, T \rbrace . $$ 
The event space is the set of all possible events where an event is any subset of the sample space. In our example, the event space is 
$$ \Sigma = \lbrace \lbrace  \rbrace, \lbrace H \rbrace, \lbrace T \rbrace, \lbrace H, T \rbrace  \rbrace. $$
Here, $\lbrace  \rbrace$ is the empty set, which tipically is denoted as $\emptyset$, and $\lbrace H, T \rbrace$ is the sample space $\Omega$. These two events are special because they are always included in the event space $\Sigma$, however the meaning of these events is not very intuitive. -->

#### Ejemplo de Dado de cuatro caras
A veces los ejemplos más triviales no son buenos para entender definiciones complejas. El ejemplo del dado hará las cosas más fáciles. Si nuestro experimento aleatorio es el de tirar un dado de cuatro caras, el espacio muestral sería:
$$ \Omega = \lbrace 1, 2, 3, 4 \rbrace.$$
Para construir el espacio de sucesos, tenemos que coger todos los posibles subconjuntos de $\Omega$:
$ \Sigma = \lbrace \lbrace \rbrace, \lbrace 1 \rbrace, \lbrace 2 \rbrace, \lbrace 3 \rbrace, \lbrace 4 \rbrace, \lbrace 1, 2 \rbrace, \lbrace 1, 3 \rbrace, \lbrace 1, 4 \rbrace, \lbrace 2, 3 \rbrace, \lbrace 2, 4 \rbrace, \lbrace 3, 4 \rbrace, \lbrace 1, 2, 3 \rbrace, \lbrace 1, 2, 4 \rbrace, \lbrace 1, 3, 4 \rbrace, \lbrace 2, 3, 4\rbrace, \lbrace 1, 2, 3, 4 \rbrace \rbrace $$
Observad que algunos de estos sucesos se pueden describir facilmente con lenguaje natural, por ejemplo, el suceso de obtener un número par se puede escribir como $\lbrace 2, 4 \rbrace$, o el suceso de obtener un número mayor que 1 se expresa en el suceso $\lbrace 2, 3, 4 \rbrace$. El conjunto $\Omega = \lbrace 1, 2, 3, 4 \rbrace$, que también pertenece a $\Sigma$, es la situación trivial en el que "sale cualquier número"; mientras que el conjunto vacío $\lbrace \rbrace = \emptyset$ es la situación imposible en la que no obtenemos ninguno de los números del dado.

<!-- ### Four-sided Dice Example
In some occasions, the most trivial examples are not good for understanding complex definitions. The dice example will make things easier. If our experiment is to throw a four-sided dice, the sample space would be:
$$ \Omega = \lbrace 1, 2, 3, 4 \rbrace.$$
To build the set of events, we have to take every subset of $\Omega$:
$$ \Sigma = \lbrace \lbrace \rbrace, \lbrace 1 \rbrace, \lbrace 2 \rbrace, \lbrace 3 \rbrace, \lbrace 4 \rbrace, \lbrace 1, 2 \rbrace, \lbrace 1, 3 \rbrace, \lbrace 1, 4 \rbrace, \lbrace 2, 3 \rbrace, \lbrace 2, 4 \rbrace, \lbrace 3, 4 \rbrace, \lbrace 1, 2, 3 \rbrace, \lbrace 1, 2, 4 \rbrace, \lbrace 1, 3, 4 \rbrace, \lbrace 2, 3, 4\rbrace, \lbrace 1, 2, 3, 4 \rbrace \rbrace $$
Note that these events can be sometimes described with natural language, for example, the event of getting an even number is denoted by $\lbrace 2, 4 \rbrace$, or the event of obtaining a number greater than 1 is denoted by the subset $\lbrace 2, 3, 4 \rbrace$. The set $\Omega = \lbrace 1, 2, 3, 4 \rbrace$, which also belongs to $\Sigma$, is the trivial situation of obtaining any number; while the empty set $\lbrace \rbrace = \emptyset$ is the impossible situation of getting none of the numbers. -->

### Probabilidad como el mapeo de eventos
La *Probabilidad* se puede describir como una medida $\mu$ que damos a cada uno de los sucesos en el espacio de sucesos $\Sigma$. Es decir, un mapeo que a cada suceso le asigna un número (un número real en $\mathbb{R}$) en función de las características de dicho evento. Esto puede expresarse cómo:
$$ \mu: \Sigma \to \mathbb{R}
    \newline
    \qquad  \quad E \to \mu(E). $$
Esta medida (o función o medida) tiene que cumplir algunos requisitos, pero nos preocuparemos por eso más adelante. En nuestro ejemplo del dado de cuatro caras, una posible elección de probabilidad es usar la llamada "medida de conteo", es decir, a cada evento le asignamos el número de elementos que contiene:
$$
\mu(\emptyset) = 0,\space
\mu(\lbrace 2 \rbrace) = 1,\space
\mu(\lbrace 3 \rbrace) = 1,\space
\mu(\lbrace 1, 3 \rbrace) = 2,\space
\mu(\lbrace 1, 3, 4 \rbrace) = 3,\space
\mu(\lbrace 1, 2, 3, 4 \rbrace) = 4 .
$$
Observad que este es sólo un posible mapeo que hemos inventado entre eventos de $\Sigma$ y los números reales $\mathbb{R}$. Podemos usar cualquier otro mapeo que cumpla los requisitos (de los que no hemos hablado aún). Uno de los requisitos es complicado y no pertenece a este capítulo, pero los otros dos requisitos son fáciles de entender:

* El conjunto vacío debe recibir probabilidad 0, es decir, nuestro mapeo, que mapea eventos de $\Sigma$ a los números reales, asigna a $\emptyset$ el número 0.
* El espacio muestral debe recibir la probabilidad de 1, es decir, nuestro mapeo asigna a $\Omega$ el número 1.

El primer requisito parece sensato, ya que el conjunto vacío representa una situación imposible (algún número saldrá en el dado). El segundo requísito también tiene mucho sentido: imaginad que tenemos también un dado de 6 caras, entonces $\mu(\Omega) = \mu(\lbrace 1, 2, 3, 4, 5, 6\rbrace) = 6$.  Es decir, la situación trivial de obtener cualquier número en el dado de 6 caras recibe un valor de 6, mientras que la misma situación trivial en el dado de cuatro caras obtiene un valor de 4. ¿Es más probable obtener lo que sea en un dado de 6 caras que en uno de 4? Por supuesto que no. Por eso se pide que estandarizar la medida al imponer $P(\Omega) = 1$.

Nuestra medida $\mu$ cumple el primer requisito, pero no el requisito de $\Omega$. Un buen truco para resolver este problema es el de definir una nueva medida llamada $\mu_P$ usando nuestra medida $\mu$ y dividiendo por $\mu(\Omega)$:
$$ \mu_P(E) = \frac{\mu(E)}{\mu(\Omega)}.$$
Ahora es fácil darse cuenta de $\mu_P(\Omega) = \frac{\mu(\Omega)}{\mu(\Omega)} = 1$, que era nuestro objetivo para definir una probabilidad correcta. Con esta modificación, nuestra medida $\mu_P$ es un mapeo de los eventos a los números reales que cumple nuestros dos requisitos: $\mu_P(\emptyset)=0$ y $\mu_P(\Omega)=1$ (además del tercer requisito del que no he escrito nada), con esto, ¡Hemos definido una probabilidad!
Ahora, la probabilidad de algunos eventos del dado de cuatro caras son:
$$
\mu(\emptyset) = 0,\space
\mu(\lbrace 2 \rbrace) = 1/4,\space
\mu(\lbrace 3 \rbrace) = 1/4,\space
\mu(\lbrace 1, 3 \rbrace) = 2/4,\space
\mu(\lbrace 1, 3, 4 \rbrace) = 3/4,\space
\mu(\lbrace 1, 2, 3, 4 \rbrace) = 4/4.
$$

## La probabilidad es una idea
> Las ideas son el principio de todas las cosas.
> 
> -- <cite>Platón.</cite>

Hasta ahora hemos definido una probabilidad para dos espacios de eventos $\Sigma$: uno describiendo los eventos de tirar una moneda y otro el de lanzar un dado de cuatro caras. La probabilidad descrita para el ejemplo de la moneda es el siguiente:
$$
\mu_P(\emptyset) = 0,\space
\mu_P(\lbrace H \rbrace) = 1/2,\space
\mu_P(\lbrace T \rbrace) = 1/2,\space
\mu_P(\lbrace H, T \rbrace) = 2/2.
$$
Esta probabilidad parece describir la probabilidad de una moneda balanceada del mundo real. Sin embargo, también podemos definir otra probabilidad válida $\mu_Q$ para los mismos eventos:
$$
\mu_Q(\emptyset) = 0,\space
\mu_Q(\lbrace H \rbrace) = 1/4,\space
\mu_Q(\lbrace T \rbrace) = 3/4,\space
\mu_Q(\lbrace H, T \rbrace) = 4/4.
$$
Esta otra probabilidad describe una moneda donde obtener cruz es tres veces más probable que obtener cara.
Usando modificaciones parecidas podemos describir infinitos mapeos válidos para estos cuatro eventos. En lo que hay que fijarse aquí es en que nosotros somos los que definimos la probabilidad, y esa probabilidad no tiene que necesariamente describir ninguna situación real. Para definir una probabilidad, no necesitamos lanzar una moneda de verdad, simplemente tenemos que saber qué es una probabilidad y qué requisitos tiene que cumplir.
Incluso es posible que una moneda perfecta, en la que cara y cruz tengan probabilidad 0.5, no exista en el mundo real. Sin embargo, nuestra moneda ideal (en el mundo de las ideas), aún sin ser real, puede ser útil para determinar algunas propiedades, hasta cierto punto, de las monedas reales.

Para entender este concepto, consideremos el círculo perfecto que está en el mundo de las ideas, descrito por Platón. Usando este círculo perfecto, podemos determinar algunas propiedades interesantes como que el perímetro y el área del círculo podemos expresarlos usando su radio como $2\pi R$ y $\pi R^2$. Un círculo del mundo real puede que no cumpla estas ecuaciones para el perímetro o el área con total exactitud, pero puede que el error sea tan pequeño que no nos importe.
En resumen, las probabilidades ideales, aquellas que describen monedas o dados perfectos, puede que no existan en la vida real, pero definimos dichas probabilidades porque es esta definición formal la que nos permite descubrir propiedades que pueden ser útiles. La definición de una probabilidad contiene toda la información sobre esta probabilidad, y por lo tanto, podemos inferir propiedades de la probabilidad al estudiar su definición.
Es decir, usamos un proceso deductivo, partimos desde una idea general, la definición de la probabilidad, y llegamos a propiedades particulares (de la probabilidad), por ejemplo la media o la varianza (las veremos más adelante).

### Probabilidad Inversa (también conocida como Estadística)
> Dios no juega a los dados con el universo.
> 
> -- <cite>Einstein.</cite>

Ahora que tenemos una intuición de qué es una probabilidad, podemos conectar este concepto con aquel que típicamente asociamos con la palabra "probabilidad". Hemos dicho que la probabilidad no está ligada al mundo real, sino que es una idea. Sin embargo, la probabilidad inversa sí está conectada al mundo real. La probabilidad inversa intenta obtener la definición de una probabilidad que controla algún experimento aleatorio en el mundo real a partir de los resultados obtenidos en repeticiones de dicho experimento.

Ahora tenemos una moneda real, una que podemos tocar y lanzar. La lanzamos 10 veces, obteniendo 3 caras y 7 cruces, ¿Qué podemos decir sobre la probabilidad de obtener cara? La respuesta más obvia es decir que $P(H) = 3/10$ y $P(T) = 7/10$. Pero, ¿Cómo de seguros estamos de esto? Ahora lanzamos la misma moneda 100 veces y los resultados son 37 caras y 63 cruces, ¿han cambiado ahora las probabilidades a $P(H) = 37/100$ y $P(T) = 63/100$?

La probabilidad inversa, también conocida como estadística (gracias a Napoleón), intenta determinar la probabilidad detraś de cualquier situación aleatoria del mundo real mediante mediciones de los resultados obtenidos. No sólo Dios juega a los dados con el universo, sino que además intentamos determinar qué eventos (recordad $\Sigma$) tiene dicho dado y la probabilidad asociada. Aún más, la estadística no se queda ahí, sino que proporciona herramientas para estimar:

* Las probabilidades detrás de experimentos o situaciones aleatorias.
* Cómo de cerca estamos en nuestras estimaciones de las probabilidades reales.
* Cómo de rápido se aproximan nuestras estimaciones a las probabilidades reales a medida que obtenemos más resultados del experimento aleatorio.

La estadística, en resumen, ofrece una forma de pensar inductiva: partimos de lo específico, los resultados del experimento aleatorio, e intentamos obtener algo general, la definición de la probabilidad que gobierna dicho experimento.

** ¿Qué es importante? **

* En cualquier experimento aleatorio tenemos un espacio de posibles resultados $\Omega$, a partir del cual se obtiene el espacio de sucesos $\Sigma$.
* Una probabilidad es un mapeo $\mu_P$ que nosotros definimos entre los eventos de $\Sigma$ y los números reales $\mathbb{R}$, que además cumple dos (más uno) requisitos:
    * El conjunto vación se mapea a 0: $\mu_P(\emptyset) = 0$
    * El espacio muestral se mapea a 1: $\mu_P(\Omega) = 1 $
* Enfatizo que nosotros definimos la probabilidad, no la inferimos de los datos. Podemos inventar una probabilidad $\mu_P$ siempre que se cumplan los requisitos.
* La probabilidad es una idea, y nos proporciona una estrategia deductiva: de una definición general podemos obtener propiedades específicas.
* La estadística estudia el proceso inverso, proporciona una estrategia inductiva: de los resultados específicos de un experimento aleatorio, intentamos inferir la definición completa de su probabilidad.
