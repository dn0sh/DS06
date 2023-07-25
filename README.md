# DAY 06 – Методы оптимизации и линейная регрессия
## Оглавление
1. [Глава I](#глава-i) \
    1.1. [Преамбула](#преамбула)
2. [Глава II](#глава-ii) \
    2.1. [Общая инструкция](#общая-инструкция)
3. [Глава III](#глава-iii) \
    3.1. [Цели](#цели)
4. [Глава IV](#глава-iv) \
    4.1. [Задание](#задание)
5. [Глава V](#глава-v) \
    5.1. [Сдача работы и проверка](#сдача-работы-и-проверка)

## Глава I
### Преамбула
Ньютон открыл нам не только закон гравитации, увидев падающее яблоко. Уехав во время пандемии к матери, 
он сфокусировался на своих трудах в том числе в области математики. Благодаря чему у нас появилось дифференциальное 
исчисление. Мы теперь умеем рассчитывать производные функций. Для многих производная — это что-то такое, 
что мы зачем-то изучали в школе. Зачем — непонятно. Там были какие-то особые правила, не всегда простые.

Оказывается, что это все-таки иногда пригождается. Например, в тех местах, где нам требуется найти наилучшее, 
оптимальное значение чего-либо — максимум или минимум. Как ты понимаешь, это для области анализа данных очень 
важно в те моменты, когда мы хотим что-то спрогнозировать с максимальной точностью или иными словами с минимальной ошибкой.

Конечно, это всё запрограммировано внутри функций разных библиотек. И когда мы вызываем метод `.predict()`, 
это всё происходит само и автоматически. Но для хорошего специалиста и профессионала важно понимать и то, что происходит 
«под капотом». Туда-то ты сегодня и заглянешь — и даже соберёшь свой небольшой моторчик.
Важным для нас понятием является градиент функции — это направление, в котором функция возрастает быстрее всего. 
Если мы будем двигаться в этом направлении, то мы быстрее придём к искомому минимуму или максимуму.


## Глава II
### Общая инструкция

Методология Школы 21 может быть не похожа на тот образовательный опыт, который случался с тобой ранее. Её отличает высокий уровень автономии: у тебя есть задача, ты должен её выполнить. По большей части тебе нужно будет самому добывать знания для её решения. Второй важный момент — это peer-to-peer обучение. В образовательном процессе нет менторов и экспертов, перед которыми ты защищаешь свой результат. Ты это делаешь перед таким же учащимися, как и ты сам. У них есть чек-лист, который поможет им качественно выполнить приемку вашей работы.

Роль Школы 21 заключается в том, чтобы обеспечить через последовательность заданий и оптимальный уровень поддержки такую траекторию обучения, при которой ты не только освоишь hard skills, но и научишься самообучаться.

- Не доверяй слухам и предположениям о том, как должно быть оформлено ваше решение. Этот документ является единственным источником, к которому стоит обращаться по большинству вопросов;
- твое решение будет оцениваться другими учащимися;
- подлежат оцениванию только те файлы, которые ты выложил в GIT (ветка develop, папка src);
- в твоей папке не должно быть лишних файлов — только те, что были указаны в задании;
- не забывай, что у вас есть доступ к интернету и поисковым системам;
- обсуждение заданий можно вести и в Rocket.Chat;
- будь внимателен к примерам, указанным в этом документе — они могут иметь важные детали, которые не были оговорены другим способом;
- и да пребудет с тобой Сила!



## Глава III
### Цели
Цель этого проекта — дать вам возможность освежить навыки расчёта производных. Но вручную вам считать не придётся: 
в Python есть классные библиотеки, которые умеют это делать автоматически. Но важно будет то, что вы воспользуетесь 
этими навыками для совершенно понятной задачи — подобрать такие значения вашей функции, которые помогут вам сделать 
наиболее точный прогноз. Кроме того, в этот проект будут вплетены и задачи на прокачку ООП (объектно-ориентированного
программирования). Про них не стоит забывать. Вам нужно будет написать свои функции, а также классы со своими методами.

## Глава IV

### Task 1
1. Установи библиотеку `sympy`.
2. Используя ее функции, напиши свою функцию, которая 
на вход примет математическую функцию `y=f(x)` вида `x**2 - x + 21`, и вернёт производную: `2𝑥−1`.

### Task 2
1. Напиши функцию, которая на вход примет математическую функцию `p = f(x, y)`, 
зависящую от двух переменных вида `(x-y)**2`, а также ту переменную, по которой нужно посчитать частную производную.
Функция должна вернуть частную производную по выбранной переменной.

### Task 3
Представь, что у нас есть истинное значений `y_true` и предсказанное значение `y_pred`, описанное линейнным уравнением вида `y_pred = w*x + b`
1. Выведи формулу квадратного отклонения между истинным и предсказанным значениями. 
2. Вычисли частные производные полученной формулы по переменным `w` и `b`.

### Task 4
Теперь мы с вами подошли к самому главному - реализации алгоритма [градиентного спуска](http://www.machinelearning.ru/wiki/index.php?title=%D0%9C%D0%B5%D1%82%D0%BE%D0%B4_%D0%B3%D1%80%D0%B0%D0%B4%D0%B8%D0%B5%D0%BD%D1%82%D0%BD%D0%BE%D0%B3%D0%BE_%D1%81%D0%BF%D1%83%D1%81%D0%BA%D0%B0).
1. В этот раз тебе нужно написать класс `Gradient()`, который будет состоять из нескольких методов. Объект при 
инициализации получает два вектора: `X`, `Y`. Далее методы обращаются к ним уже внутри класса: 
     * `predict`: на вход она получает `w`, `b`, на выход она выдаёт прогнозные значения `Y_pred`;
     * `mse`: на вход она получает `Y_pred`, на выход выдает посчитанное MSE;
     * `update`: на вход она получает `w`, `b` и `a` (наш learning rate). Сделайте по умолчанию значение `a=0.0001`. А на \ 
выходe метод выдаёт новые значения `w`, `b`, которые обновились благодаря посчитанным градиентам.
2. Проверь работу методов, подав на вход класса два вектора `X`, `Y` и начальные параметры `w`, `b` в требуемые методы.

P.S. Тут лучше все писать через numpy, потому что все вычисления будут в векторном виде. Через numpy это будет сделать удобнее)

### Task 5
Улучши код таким образом, чтобы появился метод `optimize`. На вход метод принимает num_iterations,
stopping_threshold=0.001, a=0.000001.
Метод должен итеративным образом пройти какое-то количество раз обновление значений `w`, `b`, 
придя к оптимальному значению. Критерии останова:
  * если было превышено количество заранее заданных итераций `num_iterations`;
  * если новая итерация выдала разницу между текущей ошибкой и ошибкой прошлой итерации значение, меньшее, чем `stopping_threshold`;
  * метод должен вернуть финальные значения `w`, `b`, и `mse`.


## Глава V
### Сдача работы и проверка
Сохрани решение в файле 06-assignment.ipynb \
Загрузи изменения на Git в ветку develop.

💡 [Нажми здесь](https://forms.gle/Prw35rPJ3S4hYHJg6) **чтобы отправить обратную связь по проекту**. 

