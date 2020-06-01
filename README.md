# JavaScript Style Guide
## Правило 0: Точка с запятой.
JavaScript позволяет не ставить точку с запятой, и может делать это за нас, но не следует так поступать.
Точки с запятой могут быть поставлены автоматически не там где мы можем их ожидать, что может приводить к ошибкам.
Поэтому лучше всегда ставить точку с запятой.

```javascript
// Плохо 😖
let rick = "Sanchez"
let morty = "Smith"

// Хорошо 😇
let rick = "Sanchez";
let morty = "Smith";
```
## Правило 1: Использование шаблонных строк вместо конкатенации.
Используйте шаблонные строки (разделённые символом  ` ) вместо конкатенации комплексных строк, особенно если используется несколько строковых литералов. Шаблонные строки могут занимать несколько строк.
```javascript
// Плохо 😖
function sayHi(name) {
  return 'How are you, ' + name + '?';
}

// Плохо 😖
function sayHi(name) {
  return ['How are you, ', name, '?'].join();
}

// Плохо 😖
function sayHi(name) {
  return `How are you, ${ name }?`;
}

// Хорошо 😇
function sayHi(name) {
  return `How are you, ${name}?`;
}
```
## Правило 2: Одна переменная за раз.
Каждое объявление локальной переменной объявляет только одну переменную: такие объявления, как let a = 1, b = 2; не используются.

```javascript
// Плохо 😖
let a = 1, b = 2, c = 3;
// Хорошо 😇
let a = 1;
let b = 2;
let c = 3;
``` 
## Правило 3: Одинарные кавычки, а не двойные.
Обычные строковые литералы разделяются одинарными кавычками (‘), а не двойными (“).
Совет: если строка содержит символ одинарной кавычки, попробуйте использовать шаблонные строки, чтобы не экранировать кавычки.

```javascript
// Плохо 😖
let directive = "No identification of self or mission."
// Плохо 😖
let saying = 'Say it ain\u0027t so.';
// Хорошо 😇
let directive = 'No identification of self or mission.';
// Хорошо 😇
let saying = `Say it ain't so`;
```
## Правило 4: Используйте понятные имена переменных и функций
Код гораздо легче читать, когда при его написании используют понятные, описательные имена функций и переменных. Вот не очень понятный код:
```javascript
// Плохо 😖
function avg(a) {
 let s = a.reduce((x, y) => x + y);
 return s / a.length
}
// Хорошо 😇
fuctnion averageArray(array) {
  let sum = array.reduce((number, currentSum) => number + currentSum);
  return sum / array.length;
}
```
## Правило 5: Объекты
Для создания объектов используйте фигурные скобки, а не конструктор new Object.
```javascript
// Плохо 😖
let obj = new Object();
// Хорошо 😇
let obj = {};
```
## Правило 6: Блоки кода
Используйте фигурные скобки для всех многострочных блоков.
```javascript
// Плохо 😖
if (test)
  return false;

// Хорошо 😇
if (test) return false;

// Хорошо 😇
if (test) {
  return false;
}

// Плохо 😖
function() { return false; }

// Хорошо 😇
function() {
  return false;
}
```

## Правило 7: Устанавливайте один пробел перед открывающей скобкой.
  ```javascript
  // Плохо 😖
  function test(){
    console.log('test');
  }

  // хорошо
  function test() {
    console.log('test');
  }
  ```
  ## Правило 8: Используйте программную табуляцию (ее поддерживают все современные редакторы кода и IDE) из двух пробелов.

  ```javascript
  // Плохо 😖
  function() {
  ∙∙∙∙let name;
  }

  // Плохо 😖
  function() {
  ∙let name;
  }

  // Хорошо 😇
  function() {
  ∙∙let name;
  }
  ```
  ## Правило 9: Используйте camelCase и PascalCase.
Используйте camelCase для именования объектов, функций и переменных.

  ```javascript
  // Плохо 😖
  let OBJEcttsssss = {};
  let this_is_my_object = {};
  function c() {};
  let u = new user({
    name: 'Bob Parr'
  });

  // Хорошо 😇
  let thisIsMyObject = {};
  function thisIsMyFunction() {};
  let user = new User({
    name: 'Bob Parr'
  });
  ```

Используйте PascalCase для именования конструкторов классов

  ```javascript
  // Плохо 😖
  function user(options) {
    this.name = options.name;
  }

  let bad = new user({
    name: 'Плохиш'
  });

  // Хорошо 😇
  function User(options) {
    this.name = options.name;
  }

  let good = new User({
    name: 'Кибальчиш'
  });
```
 ## Правило 10: Докуменитруйте код
Пишите хорошую документацию к своему коду — тогда тот, кто столкнётся с ним в будущем, поймёт, что и почему в этом коде делается.
```javascript
// Плохо 😖
function areaOfCircle(radius) {
  return 3,14 * radius ** 2
}
// Хорошо 😇
const pi = 3.14 // Чило Пи

function areaOfCircle(radius) {
  // Функция реализует формулу вычисления площади круга
  return pi * radius ** 2;
