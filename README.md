# Стандарт написания javaScript кода

> Ниже по тексту при выборе между es5 и es6 более приоритетным является синтаксис es6, если не указано обратное.

## Оглавление

  1. [*Определения*](./DEFINITIONS.md)
  1. [Отступы](#Отступы)

## Приведение типов
  + Для приведения к типу number использовать преимущественно унарный плюс
  + Для приведения к boolean двойное отрицание
  + В выражениях, где функция возвращает -1 в случае отстутствия значения, использовать "побитовое не" ~

## Use strict
  Директива 'use strict' рекомендована к использованию. Запрещается объявлять 'use strict' глобально (для всего кода).

  ```javascript
  // bad
  'use strict'
  ...

  // good
  function() {
      'use strict'
      ...
  }

  // good
  (function() {
      'use strict'
      ...
  })();
  ```

## Использование оператора ?:
  Запрещается использовать условный тернарный оператор ?:, если он затрудняет понимание кода

  ```javascript
  // bad
  i = i ? i < 0 ? Math.max(0, len + i) : i : 0;

  // bad
  const foo = a ? a : b;
  const bar = c ? true : false;
  const baz = c ? false : true;

  // good
  const foo = a || b;
  const bar = !!c;
  const baz = !c;
  ```


## Имена переменных и констант
  Имя должно быть на английском (**не транслитом!!!**) и должно отражать суть объекта.

  + При определении имен переменных и функций используем lowerCamelCase.
  + Имена глобальных констант пишутся заглавными буквами, в качестве разделителя между словами использовать символ нижнего подчеркивания. Локальные константы (которые существуют в рамках небольшого блока) можно именовать так же как обычные переменные.
  + Для имен конструкторов используется UpperCamelCase (PascalCase);

Объявления происходит с использованием слов *let* и *const* (var не используем). В блоке сначала объявляем константы, затем переменные без значения, потом переменные с определенным начальным значением. Переменные объявленные через let и const можно не поднимать вверх.

Запрещено использовать сокращения которые совпадают с общепринятыми. Например ie можно использовать только для Internet Explorer, а не для Inner Element и подобных. Также запрещается переиспользование и создание "универсальных" переменных (поведение которых зависит от того, в какой части кода они находятся).

  ```javascript
  // bad
  var a = 3.14159,
      TABLET = 768,
      RED = "#F00",
      GREEN = "#0F0",
      ssilka = 'http://...',
      moiTovari,
      cena;

  // bad
  function developer() {
      ...
  }
  var programmer = new developer();

  // good
  const PI = 3.14159;
  const MIN_TABLET_WIDTH = 768;
  const COLOR_RED = "#F00";
  const COLOR_GREEN = "#0F0";
  let myGoods;
  let goodsPrice;
  let goodsLink = 'http://...';

  // good
  function Developer() {
      ...
  }
  const programmer = new Developer();
  ```

## Оформление кода
Пробел не ставится:

  + внутри скобок (между открывающей и первым символом, и закрывающей и последним);
  + между именем функции и скобками с аргументами (только при вызове!);
  + между точкой с запятой и выражением;
  + между выражением и унарными операторами +, -, ++, --, !, ~, void.

В остальных случаях пробел ставится.

  ```javascript
  // bad
  let result=1;
  let i=result?1:2;
  for(var i=0;i<n;i++){result*=x;}
  if(){
      ...
  }
  function myFunction(){
      ...
  }
  alert(pow(x,n));

  // good
  let result = 1;
  let i = result ? 1 : 2;
  for (var i = 0; i < n; i++) {
      result *= x;
  }
  if () {
      ...
  }
  function myFunction() {
      ...
  }
  alert(pow(x, n));
  ```

## Выравнивание и отступы
  Для форматирования кода используются пробелы. Ширина таба - 4 пробела.


## Точка с запятой
  Точка с запятой не ставится после управляющих конструкций, анонимных и именнованных функций. В остальных случаях точка с запятой ставится в конце каждой инструкции!

  ```javascript
  // no use
  function () {
      ...
  }

  function myFunction() {
      ...
  }

  for () {
      ...
  }

  switch () {
      ...
  }

  try {
      ...
  } catch () {
      ...
  }

  if () {
      ...
  }


  // use
  let a = 1;

  const oneArray = {};

  const func = myFunction() {
      ...
  };

  (function() {
      ...
  })();
  ```

## Создание объектов
  Запрещено создавать объекты с помощью конструктора *new (Object|Array|Function)*. При их создании следует пользоваться соответствующим литералом и специальным словом const. Так же не рекомендуется использовать любые выражения подразумевающие использование eval().

  ```javascript
  // bad
  var oneObject = new Object();
  var oneArray = new Array();
  var oneFunction = new Function(аргументы, тело);
  var programmer = new Developer();

  // bad
  var oneObject = {};
  var oneArray = [];
  var function func(аргументы) {
      тело
  }

  // good
  const oneObject = {};
  const oneArray = [];
  const function func(аргументы) {
      тело
  }
  const programmer = new Developer();
  ```
