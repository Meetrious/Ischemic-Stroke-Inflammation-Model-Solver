# IschemStr

Проект призван описать инструменты для работы с математической моделью биохим. явления -- *процессов при острой фазе ишемического инсульта*. Чуть подробнее о ней [здесь](https://www.overleaf.com/read/mtxqqwygypgp). Модель описана в терминах *задачи на обыкновенные дифференциальные уравнения (в дальнейшем ОДУ) первого порядка*. 

Глобально репозиторий содержит реализацию двух программ: решение прямой задачи и решение обратной задачи в связи с первой.

## Прямая задача (*namespace StraightTask*)

Означенная заключается в *системе ОДУ с отклоняющимися аргументами первого порядка*, набором начальных условий, и начальных множеств/функций для отклоняющихся аргументов. Путём использования *метода последовательного интегрирования* (в дальнейшем **метода шагов**) объявленная задача сводится к *задаче Коши*. 

(I) Projects/ST содержит код реализации решения прямой задачи на системе из ОДУ с запаздываниями, а именно метод последовательного интегрирования поверх численных методов решений задачи Коши.

Мат. модель представляет из себя систему ОДУ с запаздываниями(или без). Уравнения конкретной системы описаны в Projects/ST/ST/includes/*models or tests*/equations.h

Поверхность алгоритма решения прямой задачи описана в Projects/ST/ST/includes/base/Solver.h

Хедеры в ST/ST/include/*Folder* организованы и включаются друг в друга в заданном порядке, который работает.
В ST/ST/ST_main.cpp включаются только те хедеры, что лежат на вершине ST/ST/includes.


## Обратная задача (*namespace ReverseTask*)
(II) Projects/RT содержит код реализации решения обратной покоэффициентной задачи поставленной на систему из ОДУ с запаздываниями, а именно стохастический метод BGA.

Input содержит необходимые входные данные для работы, такие как начальные условия, значения постоянных коэффициентов правой части уравнений по умолчанию...

Ссылка на отчёты и наработки: 
https://www.overleaf.com/read/fygdbgkzgxtz
