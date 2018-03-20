# Languages

- ![ru](https://raw.githubusercontent.com/gosquared/flags/master/flags/flags/shiny/24/Russia.png) **Russian**
- ![en](https://raw.githubusercontent.com/gosquared/flags/master/flags/flags/shiny/24/United-Kingdom.png) **English**


# Содержание
  1. [Введение](#Введение)
  2. [Ценности](#Ценности)
  3. [Каким должен быть код](#Каким-должен-быть-код)
  4. [Общие](#Общие)
  5. [Работа с файлами](#Работа-с-файлами)
  6. [Работа с переменными](#Работа-с-переменными)
  
## **Введение**
Code Conv — это правила, которые нужно соблюдать при написании кода. Мы различаем Code Style и Code Conv. Для нас Code Style — это внешний вид кода. То есть расстановка отступов, запятых, скобок и прочего. А Code Conv — это смысловое содержание кода. Правильные алгоритмы действий, правильные по смыслу названия переменных и методов, правильная композиция кода. Соблюдение Code Style легко проверяется автоматикой. А вот проверить соблюдение Code Conv в большинстве случаев может только человек.

Данные требования должны использоваться при написании любого кода. Они же используются как чек-лист при Code Review.

## **Ценности**
Главная цель Code Conv — сохранение низкой стоимости разработки и поддержки кода на длинной дистанции.

Основные ценности, помогающие достичь этой цели:

### Читаемость
Код должен легко читаться, а не легко записываться. Это значит, что такие вещи как синтаксический сахар (если он направлен на ускорение записи, а не дальнейшего чтения кода) вредны.
### Вандалоустойчивость
Код надо писать так, чтобы у разработчика, который с ним будет работать, было как можно меньше возможности внести ошибку. Например, покрывайте тестами не только краевые условия, но и кейсы, которые могут появиться в результате доработок кода и рефакторинга.
### Уменьшение энтропии
TO-DO

```Обратите внимание, что быстродействие кода не является ценностью, поэтому не самый оптимальный цикл, но удобный для понимания, будет лучше, чем быстрый, но сложный. Не нужно экономить переменные, буквы для их названий, оперативную память и так далее.```


## **Каким должен быть код**

- Понятным, явным. Явное лучше, чем неявное. Например, не должны использоваться магические методы. Также нельзя использовать exit и любые другие операторы, которые могут завершить или изменить работу процесса. 
- Удобным для использования сейчас
- Удобным для использования в будущем
- Должен стремиться к соблюдению принципов [KISS](https://ru.wikipedia.org/wiki/KISS_(%D0%BF%D1%80%D0%B8%D0%BD%D1%86%D0%B8%D0%BF)), [SOLID](https://en.wikipedia.org/wiki/SOLID_(object-oriented_design)), [DRY](https://ru.wikipedia.org/wiki/Don%E2%80%99t_repeat_yourself), [GRASP](https://ru.wikipedia.org/wiki/GRASP)
- Код должен обладать низкой связанностью и высокой связностью (подробно это описано в GRASP). Любая часть системы должна иметь изолированную логику и при надобности внешний интерфейс, который позволяет с этой логикой работать. Любая внутренняя часть должна иметь возможность быть измененной без какого-либо ущерба внешним системам 
- Код должен быть таким, чтобы его можно было автоматически отрефакторить в IDE (например, Find usages и Rename в PHPStorm). То есть должен быть слинкован типизацией и PHPDoc'ами
- В БД не должны храниться части кода (даже названия классов, переменных и констант), так как это делает невозможным автоматический рефакторинг
- Последовательным. Код должен читаться сверху вниз. Читающий не должен держать что-то в уме, возвращаться назад и интерпретировать код иначе. Например, надо избегать обратных циклов do {} while (); 
- Должен иметь минимальную [цикломатическую сложность](https://ru.wikipedia.org/wiki/%D0%A6%D0%B8%D0%BA%D0%BB%D0%BE%D0%BC%D0%B0%D1%82%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%B0%D1%8F_%D1%81%D0%BB%D0%BE%D0%B6%D0%BD%D0%BE%D1%81%D1%82%D1%8C)
