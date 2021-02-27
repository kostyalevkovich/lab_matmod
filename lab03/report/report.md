---
# Front matter
lang: ru-RU
title: "Лабораторная работа №3"
subtitle: "Модель боевых действий"
author: "Левкович Константин Анатольевич"

# Formatting
toc-title: "Содержание"
toc: true # Table of contents
toc_depth: 2
lof: true # List of figures
lot: true # List of tables
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

Познакомиться с простейшими моделями боевых действий - моделями Ланчестера. 

# Задание

Между страной Х и страной У идет война. Численность состава войск исчисляется от начала войны, и являются временными функциями
$x(t)$ и $y(t)$. В начальный момент времени страна Х имеет армию численностью 87 700 человек, а в распоряжении страны У армия численностью в 91 400 человек. Для упрощения модели считаем, что коэффициенты $a,b,c,h$ постоянны. Также считаем $P(t)$ и $Q(t)$ непрерывные функции.

Постройте графики изменения численности войск армии Х и армии У для следующих случаев:


1. Модель боевых действий между регулярными войсками:

$$ \frac{\partial x}{\partial t} = -0.354x(t) - 0.765y(t) + |sin(t+10)|$$
$$ \frac{\partial y}{\partial t} = -0.679x(t) - 0.845y(t) + |cos(t+15)|$$

2. Модель ведение боевых действий с участием регулярных войск и партизанских отрядов:

$$ \frac{\partial x}{\partial t} = -0.505x(t) - 0.77y(t) + sin(2t) + 2$$
$$ \frac{\partial y}{\partial t} = -0.6x(t)y(t) - 0.404y(t) + cos(5t) + 2$$

# Выполнение лабораторной работы

## Решение задачи
1. Для начала задаем необходимые коэффициенты: эффективность боевых действий со стороны $у$ и $х$ соответственно, величины, характеризующие степень влияния различных факторов на потери, возможность подхода подкрепления к войскам в течение одного дня.


2. Задаем время боевых действий: начальный момент, предельный, а также шаг изменения времени. Мы будем использовать 0 за начальный момент, 1 за предельный с шагом в 0.05. 


3. Во втором случае в борьбу добавляются партизанские отряды. Нерегулярные войска в отличии от постоянной армии менее уязвимы, так как действуют скрытно, в этом случае сопернику приходится действовать неизбирательно, по площадям, занимаемым партизанами. Поэтому считается, что тем потерь партизан, проводящих свои операции в разных местах на некоторой известной территории, пропорционален не только численности армейских соединений, но и численности самих партизан.


4. В простейшей модели борьбы двух противников коэффициенты
$b(t)$ и $c(t)$ являются постоянными. Также не учитываются потери, не связанные с боевыми действиями, и возможность подхода подкрепления, поэтому модель принимает жесткий вид, допускающая точное решение $$ \frac{\partial x}{\partial y} = \frac{by}{cx}$$


5. Подставляя и решая в уравнение исходные данные, можем построить график, взяв зависимость от времени.


![Первая модель](image/Первая.png){ #fig:001 width=70% }

![Вторая модель](image/Вторая.png){ #fig:001 width=70% }


# Выводы

  1. Вывел дифференциальные уравнения, описывающее простейшую модель боевых действий.
  2. Построил график зависимости численности армий от времени.

