<!--
.. title: What is Probability?
.. slug: what-is-probability
.. date: 2020-06-26 09:32:29 UTC+02:00
.. tags: 
.. category: 
.. link: 
.. description: 
.. type: text
.. has_math: yes
-->


# Chapter 0
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
However, this is actually closer to statistics than to probability. This part is tricky, so for a better understanding we will forget about statistics and we will discuss about probability and, if necessary, inverse probability.


## Sample Space and Event Space
To define probability, it is necessary to define the *sample space* $\Omega$ of an experiment, and also the *event space* $\Sigma$. The sample space is the set of all possible outcomes of a certain experiment or random trial. 
### Coin Example
Imagine that our experiment is the toss of a coin, then the sample space is 
$$ \Omega = \lbrace Head, Tail \rbrace = \lbrace H, T \rbrace . $$ 
The event space is the set of all possible events where an event is any subset of the sample space. In our example, the event space is 
$$ \Sigma = \lbrace \lbrace  \rbrace, \lbrace H \rbrace, \lbrace T \rbrace, \lbrace H, T \rbrace  \rbrace. $$
Here, $\lbrace  \rbrace$ is the empty set, which tipically is denoted as $\emptyset$, and $\lbrace H, T \rbrace$ is the sample space $\Omega$. These two events are special because they are always included in the event space $\Sigma$, however the meaning of these events is not very intuitive.

### Four-sided Dice Example
In some occasions, the most trivial examples are not good for understanding complex definitions. The dice example will make things easier. If our experiment is to throw a four-sided dice, the sample space would be:
$$ \Omega = \lbrace 1, 2, 3, 4 \rbrace.$$
To build the set of events, we have to take every subset of $\Omega$:
$$ \Sigma = \lbrace \lbrace \rbrace, \lbrace 1 \rbrace, \lbrace 2 \rbrace, \lbrace 3 \rbrace, \lbrace 4 \rbrace, \lbrace 1, 2 \rbrace, \lbrace 1, 3 \rbrace, \lbrace 1, 4 \rbrace, \lbrace 2, 3 \rbrace, \lbrace 2, 4 \rbrace, \lbrace 3, 4 \rbrace, \lbrace 1, 2, 3 \rbrace, \lbrace 1, 2, 4 \rbrace, \lbrace 1, 3, 4 \rbrace, \lbrace 2, 3, 4\rbrace, \lbrace 1, 2, 3, 4 \rbrace \rbrace $$
Note that these events can be sometimes described with natural language, for example, the event of getting an even number is denoted by $\lbrace 2, 4 \rbrace$, or the event of obtaining a number greater than 1 is denoted by the subset $\lbrace 2, 3, 4 \rbrace$. The set $\Omega = \lbrace 1, 2, 3, 4 \rbrace$, which also belongs to $\Sigma$, is the trivial situation of obtaining any number; while the empty set $\lbrace \rbrace = \emptyset$ is the impossible situation of getting none of the numbers.

### Probability as a mapping of events
*Probability* can be described as a measure $\mu$ that we give to each of the events in the space of events $\Sigma$. That is, a mapping that assigns each event a number (a real number in $\mathbb{R}$), depending on the characteristics of this event. This can be expressed as
<!-- $$ 
\begin{aligned}
    \mu: &\Sigma &\to &\mathbb{R}
    \newline
    &E &\to &\mu(E) = E
\end{aligned}
$$ -->
$$ \mu: \Sigma \to \mathbb{R}
    \newline
    \qquad  \quad E \to \mu(E) $$
This measure (or function or mapping) has to fulfill some requirements, but we will worry about that later. In our example of the four-sided dice, one possible choice of probability is to use what is called the "counting measure", that is, we assign to each event the number of elements that it contains:
$$
\mu(\emptyset) = 0,\space
\mu(\lbrace 2 \rbrace) = 1,\space
\mu(\lbrace 3 \rbrace) = 1,\space
\mu(\lbrace 1, 3 \rbrace) = 2,\space
\mu(\lbrace 1, 3, 4 \rbrace) = 3,\space
\mu(\lbrace 1, 2, 3, 4 \rbrace) = 4 .
$$
Observe that this is just one possible mapping that we have invented between the events of $\Sigma$ and the numbers . We can come out with any mapping that fulfills the requirements we have not talked about yet. One of the requirements is tricky and does not belong to this layer, but the other two requirements are easy to understand:

* The empty set must receive probability 0, that is our mapping, which maps events from $\Sigma$ to the real numbers, maps $\emptyset$ to the number 0.
* The whole sample space must receive a probability of 1, that is our mapping, which maps events from $\Sigma$ to the real numbers, maps $\Omega$ to the number 1.

The first requirement seems very sensible, since we have said that the empty set represents an impossible situation. The second requirement also makes a lot of sense: imagine that we have a six-sided dice, then $\mu(\Omega) = \mu(\lbrace 1, 2, 3, 4, 5, 6\rbrace) = 6$. That is, the trivial situation of obtaining any number on a six-sided dice receives the value of 6, while the same trivial situation in the four-sided dice receives a value of 4. Is it more likely to obtain any number in the six-sided dice? Of course not. That is why we ask to standardize the measure by imposing $P(\Omega) = 1$.

Our counting measure $\mu$ fulfills the empty set requirement, but not the $\Omega$ requirement. One neat trick to solve this issue is to define a new measure called $\mu_P$ using our measure $\mu$ and dividing by $\mu(\Omega)$:
$$ \mu_P(E) = \frac{\mu(E)}{\mu(\Omega)}.$$
Now, it is easy to check that $\mu_P(\Omega) = \frac{\mu(\Omega)}{\mu(\Omega)} = 1$, which was our goal to define a proper probability. With this modification, our measure $\mu_P$ is a mapping from the events to the real numbers that fulfills our two requirements: $\mu_P(\emptyset)=0$ and $\mu_P(\Omega)=1$ (and the more complex requirement too), so we have built a probability!
Now, the probability measures of some events of the four-sided dice example are
$$
\mu(\emptyset) = 0,\space
\mu(\lbrace 2 \rbrace) = 1/4,\space
\mu(\lbrace 3 \rbrace) = 1/4,\space
\mu(\lbrace 1, 3 \rbrace) = 2/4,\space
\mu(\lbrace 1, 3, 4 \rbrace) = 3/4,\space
\mu(\lbrace 1, 2, 3, 4 \rbrace) = 4/4.
$$
We can also use this definition of $\mu_P$ to build a probability for the coin toss, but now we take into account that $\mu(\Omega) = 2$, then:
$$
\mu_P(\emptyset) = 0,\space
\mu_P(\lbrace H \rbrace) = 1/2,\space
\mu_P(\lbrace T \rbrace) = 1/2,\space
\mu_P(\lbrace H, T \rbrace) = 2/2.
$$

### Probability is an idea
> Ideas are the source of all things.
> 
> -- <cite>Plato.</cite>

Until now we have defined a probability for two event spaces $\Sigma$: one describing the events of tossing a coin and other describing those of rolling a dice. The one describing the events of tossing a coin is described as:
$$
\mu_P(\emptyset) = 0,\space
\mu_P(\lbrace H \rbrace) = 1/2,\space
\mu_P(\lbrace T \rbrace) = 1/2,\space
\mu_P(\lbrace H, T \rbrace) = 2/2.
$$
This probability seems to describe the probability of a real balanced coin. However, we could also define other valid probability mapping $\mu_Q$ for the same events:
$$
\mu_Q(\emptyset) = 0,\space
\mu_Q(\lbrace H \rbrace) = 1/4,\space
\mu_Q(\lbrace T \rbrace) = 3/4,\space
\mu_Q(\lbrace H, T \rbrace) = 4/4.
$$
This other probability mapping describes a coin where getting tails is three times more probable than getting heads.
Using similar modifications we could describe infinitely many valid probability mappings for these four events. The important thing to notice is that we are the ones describing the probability, and that probability does not necessarily need to describe a real situation. To define a probability we do not need to toss a real coin. Moreover, a perfect coin, where getting tails and heads have exactly 0.5 probability each, may not exist in real life. But this ideal coin is useful to determine some properties that could be expected, to some degree, in a real coin. 
<!-- Let go back to the dice example, if we wish to know the probability of getting an odd number in an ideal dice, we just have to see our definition of $\mu_P(\lbrace 1, 3, 5 \rbrace)$. -->

To understand this concept, consider the ideal circle that lives in the world of ideas of Plato. Using this perfect circle we can determine some useful properties such as the perimeter $2\pi R$ or the area of the circle $\pi R^2$. A circle of the real world might not have an area equal to $\pi R^2$, however the error might be so small that we can ignore it.
In short, ideal probabilities, such as those concerning perfect coins or dices may not exist in real life, but we define those probabilities because the definition is our tool to discover the properties of the probability. The definition has all the information, it describes completely the probability, and therefore, we can infer properties of that probability using its definition.
That is, we use a deductive process, we go from the more general view, the definition, to more specific properties, e.g. mean, variance (we will those in other chapter).

### Inverse Probability (a.k.a. Statistics)
> God does not play dice with the universe.
> 
> -- <cite>Einstein.</cite>

Now that we have an intuition of what a probability is, we can connect this concept to what we typically associate with the word "probability". We have said that probability is not tied to the real world, but it is an idea. However, inverse probability is connected to the real world. Inverse probability is trying to get the definition of the probability governing some real world experiment by observing the outcomes of that experiment.

Now we have a real coin, one that we can touch and actually toss. We toss it 10 times, obtaining 3 heads and 7 tails, what can we say about the probability of getting heads? The obvious answer is to say $P(H) = 3/10$ and $P(T) = 7/10$. But, how sure are we about this? We now toss the same coin 100 times and the results are 37 heads and 63 coins, have now the probabilities change to $P(H) = 37/100$ and $P(T) = 63/100$?

Inverse probability, also known as Statistics (thanks to Napoleon), tries to determine the probability behind every random situation in the real world by measuring the outcomes of this situation. Not only God does play dice with the universe, we also try to determine the events (remember $\Sigma$) of such dice and its probability.
Moreover, Statistics (or Inverse Probability) does not stop there, it provides a way of estimating:

* The probabilities behind random experiments or situations.
* How close we are to the real probabilities (of God's dice)
* How fast do we approach those real probabilities as we gather more and more outcomes.

Statistics provide an inductive way of thinking, we go from the specifics, that is, the outcomes of some experiments, and we try to infer the general view: the definition of the probability behind that experiment.

** What is important? **

* In any random experiment we have a space of possible outcomes $\Omega$, and from this space $\Omega$ we can construct the space of events $\Sigma$. 
* A probability is a mapping $\mu_P$ that we define between the events in $\Sigma$ and the real numbers $\mathbb{R}$, which fulfills two (plus one unknown) requirements:
    * The empty set is mapped to 0: $\mu_P(\emptyset) = 0$
    * The sample space is mapped to 1: $\mu_P(\Omega) = 1 $
* I emphasize that we define a probability, we do not infer it from data. We can invent any probability $\mu_P$ as long as the requirements are met.
* Probability is an idea, and it provides us with a deductive strategy: from the general definition we can obtain specific properties.
* Statistic study the inverse process, it provides an inductive strategy: from the specific outcomes of a random experiment, we try to infer its complete probability definition.