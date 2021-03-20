---
# Front matter
lang: ru-RU
title: "Лабораторная работа №6"
subtitle: "Задача об эпидемии"
author: "Левкович Константин Анатольевич"

# Formatting
toc-title: "Содержание"
toc: true # Table of contents
toc_depth: 2
lof: true # List of figures
fontsize: 12pt
linestretch: 1.5
papersize: a4paper
documentclass: scrreprt
polyglossia-lang: russian
polyglossia-otherlangs: english
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase
indent: true
pdf-engine: lualatex
header-includes:
  - \linepenalty=10 # the penalty added to the badness of each line within a paragraph (no associated penalty node) Increasing the value makes tex try to have fewer lines in the paragraph.
  - \interlinepenalty=0 # value of the penalty (node) added after each line of a paragraph.
  - \hyphenpenalty=50 # the penalty for line breaking at an automatically inserted hyphen
  - \exhyphenpenalty=50 # the penalty for line breaking at an explicit hyphen
  - \binoppenalty=700 # the penalty for breaking a line at a binary operator
  - \relpenalty=500 # the penalty for breaking a line at a relation
  - \clubpenalty=150 # extra penalty for breaking after first line of a paragraph
  - \widowpenalty=150 # extra penalty for breaking before last line of a paragraph
  - \displaywidowpenalty=50 # extra penalty for breaking before last line before a display math
  - \brokenpenalty=100 # extra penalty for page breaking after a hyphenated line
  - \predisplaypenalty=10000 # penalty for breaking before a display
  - \postdisplaypenalty=0 # penalty for breaking after a display
  - \floatingpenalty = 20000 # penalty for splitting an insertion (can only be split footnote in standard LaTeX)
  - \raggedbottom # or \flushbottom
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

1. Рассмотреть простейшую модель эпидемии.

2. Построить графики изменения числа особей в каждой из трех групп.

3. Рассмотреть, как будет протекать эпидемия.


# Выполнение лабораторной работы

## Теоретическое введение

Предположим, что некая популяция, состоящая из N особей, (считаем, что популяция изолирована) подразделяется на три группы. Первая группа - $S(t)$ — восприимчивые к болезни, но пока здоровые особи. Вторая - $I(t)$ — это число инфицированных особей, которые также при этом являются распространителями инфекции. И третья - $R(t)$ — это здоровые особи с иммунитетом к болезни.  


До того, как число заболевших не превышает критического значения $I^*$ считаем, что все больные изолированы и не заражают здоровых. Когда $I(t)>I^*$, тогда инфицирование способны заражать восприимчивых к болезни особей.

Таким образом, скорость изменения числа S(t) меняется по следующему закону:

$$ \frac{\partial S}{\partial t} = \begin{cases} - \alpha S, если I(t)>I^* \\ 0, если I(t) \leq I^* \end{cases}$$

Поскольку каждая восприимчивая к болезни особь, которая, в конце концов, заболевает, сама становится инфекционной, то скорость изменения числа инфекционных особей представляет разность за единицу времени между заразившимися и теми, кто уже болеет и лечится, т.е.:

$$ \frac{\partial I}{\partial t} = \begin{cases} - \alpha S - \beta I, если I(t)>I^* \\ - \beta I, если I(t) \leq I^* \end{cases}$$

А скорость изменения выздоравливающих особей (при этом приобретающие иммунитет к болезни)

$$ \frac{\partial R}{\partial t} = \beta I$$

Постоянные пропорциональности:

- $\alpha$ — коэффициент заболеваемости

- $\beta$ — коэффициент выздоровления

 Для анализа картины протекания эпидемии необходимо рассмотреть два случая: $I(0) \leq I^*$ и $I(0) > I^*$

## Задание

На одном острове вспыхнула эпидемия. Известно, что из всех проживающих на острове $(N=8439)$ в момент начала эпидемии $(t=0)$ число заболевших людей
(являющихся распространителями инфекции) $I(0)=86$, А число здоровых людей с
иммунитетом к болезни $R(0)=25$. Таким образом, число людей восприимчивых к
болезни, но пока здоровых, в начальный момент времени $S(0)=N-I(0)- R(0)$.  
Постройте графики изменения числа особей в каждой из трех групп.
Рассмотрите, как будет протекать эпидемия в случае:  
1. если $I(0) \leq I^*$  
2. если $I(0) > I^*$

$$ \alpha = 0.35 $$
$$ \beta = 0.13 $$


## Графики

Динамика изменения числа людей в каждой из трех групп в случае, когда $I(0) \leq I^*$ с начальными условиями $I(0)=86$, $R(0)=25$, $S(0)=8328$.
Коэффициенты $\alpha = 0.35$, $\beta = 0.13$. (рис. -@fig:001). График изменения числа людей в группе здоровых людей с иммунитетом, а также в группе инфицированных особей (рис. -@fig:002).

![Первый случай](image/первый.png){ #fig:001 width=70% }

![Первый случай без S(0)](image/первый_1.png){ #fig:002 width=70% }

Динамика изменения числа людей в каждой из трех групп в случае, когда $I(0) > I^*$ с начальными условиями $I(0)=86$, $R(0)=25$, $S(0)=8328$.
Коэффициенты $\alpha = 0.35$, $\beta = 0.13$. (рис. -@fig:003)

![Второй случай](image/второй.png){ #fig:003 width=70% }

# Выводы

1. Построил графики изменения числа особей в каждой из трех групп.

2. Рассмотрел, как будет протекать эпидемия в разных случаях.