# Автор ревью
Сорочан И.В. Б20-505

# Общие замечания
Нет пространства имен


## Cissoid.h
`Cissoid.h:6` - объявлять пи нет необходимости. В стандартной библиотеке уже объявлено несколько констант, связанных с ней. Просто пи - `M_PI` (из `cmath`)

Использование `this->` не обязательно (вместо `this->a` просто `a`)


## Cissoid.cpp
Строки 4, 14, 18, 22, 26 - используются геттеры внутри метода класса (просто `a` вместо `get_a()`).

Не понятно как используются `sqrt`, `pow`, `sin`, `cos`, - нет директивы `using` (в хедере тоже нет).

Об использовании константы `M_PI` и прочих уже написано выше, подробнее про них можно прочитать [здесь](https://www.quantstart.com/articles/Mathematical-Constants-in-C/)


## UI.h
`get_num` не обрабатывает случай `bad`, только `eof` и `fail`
Так же передача статуса отработки функции в возвращаемом значении - плохой тон (лучше уж выкинуть исключение)

Почему все поля и методы `public`, как минимум cissoid должен быть `private`?

Почему используется `Cissoid *`, а не `Cissoid`. Тогда можно было бы и без конструкторов-деструкторов в `UI` обойтись. Да и не понятно зачем вообще нужно динамическое выделение памяти - самих динамических параметров то нет.

`UI.h:44` - функция диалога это хорошо, но если возможно было бы круто использовать паттерн команда (но не обязательно, просто замечание).


## UI.cpp
В целом кроме форматирования замечаний нет.

Про сишный подход с функцией `dialog` и `start` (и паттерном команда) уже писал.

### Код
Старый код можно найти [здесь](https://github.com/Klimonov23/OOP_Cissoid/tree/bd6cb48696db89acee6e0cb17779752a44fb1aa0)