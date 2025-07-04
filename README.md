# Мельников Илья Никитович, ИТ-9, Вариант 7 
# Проект: Игра «Пьяница»

## Описание проекта
Данный проект представляет собой реализацию игры «Пьяница» на языке Python.  
Программа моделирует карточную игру для двух игроков по упрощённым правилам.  
Реализация выполнена с использованием объектно-ориентированного подхода и стандартных средств языка, без внешних библиотек.

Правила игры:
- У каждого игрока изначально по 5 уникальных карт от 0 до 9 (всего 10 разных карт).
- На каждом ходу оба игрока вскрывают верхнюю карту.
- Побеждает карта с большим значением, за исключением случая: 0 бьёт 9.
- Победитель кладёт в конец своей колоды сначала свою карту, затем карту соперника.
- Игра продолжается до тех пор, пока у одного из игроков не закончатся карты, либо пока не будет превышено 10⁶ ходов (в этом случае ничья: "botva").
  
## Требования
- Python 3.x
- Используются только встроенные модули (`collections`)
- Код соответствует базовому PEP 8 и требованиям оформления в рамках учебной работы

## Алгоритм и идея решения
1. Программа считывает две строки по 5 чисел — колоды двух игроков.
2. Выполняется валидация ввода (длина, диапазон значений, уникальность всех карт от 0 до 9).
3. Каждая колода реализована в виде очереди (`deque`).
4. В цикле по ходам:
   - Игроки вскрывают верхние карты.
   - Сравниваются карты (с учётом особого правила "0 бьёт 9").
   - Победитель получает обе карты и кладёт их в конец своей колоды.
5. Игра завершается при потере всех карт одним из игроков или при достижении лимита в 10⁶ ходов.
6. Результат выводится в формате: `first X`, `second X` или `botva`.

## Инструкции
1. Запустите файл `drunkard.py` через команду `python drunkard.py`.
2. Следуйте текстовым подсказкам в терминале.
3. Введите 5 чисел для первого игрока и 5 чисел для второго.
4. Получите результат — кто победил и за сколько ходов.

## Особенности реализации
- Реализовано два класса: `Player` и `DrunkardGame` для удобства и структурности.
- Включена проверка пользовательского ввода и обработка исключений (`ValueError`, `KeyboardInterrupt`).
- Программа завершает работу корректно даже при ошибках ввода или ручной остановке.
- Добавлены строковые документации (docstrings) для всех классов и функций.
- Очередь реализована через `collections.deque` — эффективно и по смыслу (FIFO).
- Поддержка вывода `botva` при зацикливании игры (что на практике не случается).
