# js-code-standart

Данный стандарт основывается в первую очередь на простоте.
Какой-то текст


## Оглавление

  1. [Отступы](#Отступы)
  1. [Отступы](#Отступы)

## Отступы
  Для форматирования кода используются пробелы. Ширина таба - 4 пробела.

**[⬆ К оглавлению](#Оглавление)**

## Оформление операторов
  Во всех операторах, кроме унарных, между оператором и переменными (строковыми или числовыми литералами) ставится пробел.

## Точка с запятой
  Точка с запятой ставится после всех выражений

**[⬆ К оглавлению](#Оглавление)**

## Объявление переменных
  > При объявлении переменных используем синтаксис es6.

  ### Объявления через let и const не группируем. Сначала объявляем константы, затем переменные без значения, потом переменные с определенным начальным значением.

    ```javascript
    // bad
    let i, len, dragonball, x = 20,
        items = getItems(),
        goSportsTeam = true;

    // bad
    let i;
    const items = getItems();
    let dragonball;
    let x = 20,
    const goSportsTeam = true;
    let len;

    // good
    const goSportsTeam = true;
    const items = getItems();
    let dragonball;
    let i;
    let length;
    let x = 20;
    ```

  ### Для объявления *объектных типов* (массивы, объекты, функции) используем const. Если не очевиден выбор между let и const, то используем let.

    ```javascript
    // bad
    superPower = new SuperPower();

    // good
    const superPower = new SuperPower();
    ```

**[⬆ К оглавлению](#Оглавление)**


## Имена переменных и констант
  При определении имен переменных и функций используем [camelCase синтаксис](https://ru.wikipedia.org/wiki/CamelCase). Первый символ в нижнем регистре. Имя должно быть на английском (**не транслитом!!!**). Имя должно отражать суть переменной. Имена глобальных констант пишутся заглавными буквами, в качестве разделителя между словами использовать символ нижнего подчеркивания. Локальные константы (которые существуют в рамках небольшого блока) можно именовать так же как обычные переменные.

    ```javascript
    // bad
    const a = 3.14159;
    const B = 768;

    // bad
    const a = 1, b = 1;

    // good
    const PI = 3.14159;
    const MIN_TABLET_WIDTH = 768;
    ```


**[⬆ К оглавлению](#Оглавление)**

  Lorem ipsum dolor sit amet, consectetur adipisicing elit. Suscipit ipsa veritatis ratione asperiores eum iure blanditiis laudantium itaque laboriosam corrupti inventore explicabo fuga adipisci quaerat, ad amet nobis beatae dolorem ab, iusto laborum doloribus iste. Eius veniam nobis quia expedita repellat ipsa eos, et harum repudiandae delectus tempora animi quam fugiat hic voluptates officiis laborum, illo dolore architecto, repellendus omnis. Veniam in placeat, numquam eius omnis tempora enim dolorum temporibus pariatur asperiores tenetur hic debitis mollitia voluptas velit, illo laboriosam quia consectetur modi. Mollitia nulla quidem, minima soluta voluptas, placeat voluptates tenetur expedita sed unde libero fuga officiis illum qui et fugiat quo aspernatur fugit explicabo. Quae corporis excepturi explicabo et mollitia quia ad qui ab velit, quasi harum magnam minima asperiores laborum maiores eius dolorum quidem adipisci doloribus minus molestiae assumenda odit repellat sapiente dicta. Praesentium ex fugiat, mollitia assumenda sapiente porro dolorem numquam non aperiam distinctio, iste, libero.

**[⬆ К оглавлению](#Оглавление)**