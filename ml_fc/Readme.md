#Прогнозирования добычи нефти с помощью методов машинного обучения

Вопрос предсказания добычи скважинами нефти и газа  является одним из самых важных  в нефтяной и газовой промышленности. Без обоснованного прогноза добычи невозможно принимать решения о рентабельности проектов, капитальных вложениях, бурении новых и эксплуатации существующих скважин.

**Спойлер: обзор для не нефтников/газовиков**

В настоящий момент кроме классического аналитического способа оценки  (эксель + метод матбаланса, на котором мы не будем останавливаться) общепринятым является построение геологической (статической) и гидродинамической (динамической) моделей, на основе которой принимаются решения.

Типичный профиль добычи нефти выглядит вот так:

*pic*

###Геологическое моделирование

###Гидродинамическое моделирование

Гидродинамическая модель в 3D выглядит вот так:

*pic*

##Идея использования машинного обучения

Недостаток подхода с построением полноценной гидродинамической модели в том, что на постройку модели нужно очень много времени (от нескольких месяцев до года и даже больше). Это зависит от количества скважин и имеющихся данных по месторождению. Более того, построенная гидродинамическая модель (ГДМ) является сложной системой с высокой чувствительностью к входным данным. Поэтому любая некорректность в данных может привести к отличающимся результатам, что не удивительно, когда данных по месторождениям протяженность которых многие километры получают через скважины диаметром около 10 см. Скважины в свою очередь, пробурены на глубины порядка 3-х километров и на расстояниях 250-1000 метров друг от друга. Таким образом строя модель месторождения, мы делаем выводы о многокилометровых подземных хранилищах нефти и газа по информации полученной через "точечные уколы"

Поэтому идея попробовать использовать более "простые" методы, например такие как, машинное обучение прямо скажем витает в воздухе.

**Отступление. Что такое скважинные данные**

*Определение*: Скважина - это цилиндрическая горная выработка, длинной многократно превышающей её диаметр. Это не совсем дырка в земле. Типично - это 3-х километровое отверстие в которую спущены несколько вложенных друг в друга колонн обсадных труб (для предотвращения обвалов). Пространство между колоннами обсадных труб и горной породой для герметичности дополнительно цементируется.

Скважинные данные включают в себя:

* данные полученные при спуске приборов в скважину (например давление, температура, глубина и протяжённость нефте/газо-насыщенного пласта, кажущееся сопротивление породы, радиоактивность и прочие..),

* замеряемые на поверхности - количество добываемых нефти, газа и попутной воды, их состав.


В данном случае скважины нефтяные, а значит на поверхности мы получаем нефть с растворённым в ней газом и попутную воду. Как правило в начале эксплуатации скважин добывается чистая нефть, но позже скважина обводняется и доля воды увеличивается, пока скважина не перестаёт быть рентабельной. Обводнённость чаще выражают в процентах и рассчитывают как отношение количества добытой воды к добытой жидкости т.е. Qнефти/(Qнефи + Qводы)*100%

**Конец спойлера**

- Обводнённость

- Интервал перфорации
- Координаты скважины

##Постановка задачи

Создать модель машинного обучения, которая по имеющимся скважинным данным и проверить, что модель сможет предсказать:

- обводнённость существующих скважин

- обводнённость и дебит нефти скважин-кандидатов на бурение

##Этапы

- Создание **MVP** (minimal viable product)
- Проверить, что модель предсказывает необходимые параметры.
- Масштабировать модель на большее количество скважин в случае положительного результата













### Примечания

1. Цель исследования была в том чтобы понять применимость методов машинного обучения в этой области. Задача выбрать наилучший алгоритм не ставилась, поэтому сравнение наилучшего алгоритма не проводилось

2. Исходные данные для проведения расчётов выложить не могу. У меня нет разрешения для публикации геологических данных.