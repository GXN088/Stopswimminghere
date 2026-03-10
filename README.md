# Stopswimminghere
Давай напишем программу, которая определит, что умеют делать жители океана:

Подумай, как связаны интерфейсы CanSwim (способен плавать) и CanWalk (способен ходить) с классом SeaCreature (морское животное).
Правильно расставь наследование интерфейсов и класса SeaCreature.
Подумай, как могут быть связаны классы Orca (Косатка), Whale (Кит), RiverOtter (Выдра) с классом SeaCreature.
Расставь правильно наследование между классами Orca, Whale, RiverOtter и классом SeaCreature.
У выбранных классов реализуй метод getCurrentCreature, чтобы он возвращал объект у которого его вызвали.
Подумай, какой класс должен реализовать интерфейс CanWalk и добавить интерфейс этому классу.
Подумай, какое животное еще не умеет плавать и добавить ему интерфейс CanSwim.


Псевдокод:

```
ПРОГРАММА

main
    creature = новый Orca
    creature.swim()

    creature = новый Whale
    creature.swim()

    creature = новый RiverOtter
    creature.swim()
КОНЕЦ main


ФУНКЦИЯ test(creature: CanSwim)
    creature.swim()
КОНЕЦ


ИНТЕРФЕЙС CanWalk
    метод walk()
КОНЕЦ


ИНТЕРФЕЙС CanSwim
    метод swim()
КОНЕЦ


АБСТРАКТНЫЙ КЛАСС SeaCreature

    метод swim()
        currentCreature = getCurrentCreature()
        вызвать currentCreature.displaySwim()
    КОНЕЦ

    приватный метод displaySwim()
        вывести имя класса текущего существа + " is swimming"
    КОНЕЦ

    абстрактный метод getCurrentCreature() : CanSwim

КОНЕЦ


КЛАСС Orca наследует SeaCreature и реализует CanSwim

    метод getCurrentCreature()
        вернуть this
    КОНЕЦ

КОНЕЦ


КЛАСС Whale наследует SeaCreature и реализует CanSwim

    метод getCurrentCreature()
        вернуть this
    КОНЕЦ

КОНЕЦ


КЛАСС RiverOtter реализует CanWalk и CanSwim

    метод swim()
        ничего не делает
    КОНЕЦ

    метод walk()
        ничего не делает
    КОНЕЦ

КОНЕЦ
```

### Что происходит по смыслу

* `Orca` и `Whale` — морские существа → используют логику `SeaCreature.swim()`
* `SeaCreature.swim()` печатает
  **"Orca is swimming"** или **"Whale is swimming"**
* `RiverOtter` сам реализует `swim()` → но метод пустой → ничего не выводится.

Итого вывод программы:

```
Orca is swimming
Whale is swimming
```

Выдра тихо себе плывёт.🦫
