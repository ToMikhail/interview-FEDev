# Questions Extra from Andersen   

- ## Autoboxing   
>Почему у примитивов мы можем вызвать метод ( для примера ***.length***). Это происходит потому что для каждого типа существует и создается конструктор, который упаковывает примитивный тип в обект(и соответсвенно все эти методы вызываеются не у примтивног типа а у его объекта прототипа).  
```
// const str = 'hello'
const str = new String('hello') // string
// const str = 'hello'
console.log( typeof str); // object
```
>Распоковка происходит у всех объектов, не зависимо, каким типом является объект (примитивным или нет). Вызывается меотд valueof().   

- ## Методы глубокого копирования данных  
>Существует несколько методов для глубокого копирования данных(не ссылки скопировать а полное слонирование объекта):  
>   * Метод JSON.strongify(value) + JSON.parse(value);
>   * Новый метод structuredClone(value);
>   * просто перебрать массив методом перебора (for)
   
- ## Всплытие переменных и функций(Hoisting)   
> Отличия let, const и var. Объявления let и const имеют блочное копирование, что означает, что они доступны только в пределах { }, окружающих их. var, с другой стороны, не имеет такого ограничения.
```
let babyAge = 1;
let isBirthday = true;

if (isBirthday) {
	let babyAge = 2; 
}

console.log(babyAge); // output 1

var babyAge = 1;
var isBirthday = true;

if (isBirthday) {
	var babyAge = 2; 
}

console.log(babyAge); // output 2
```

>Последнее существенное различие между let / const и var заключается в том, что если вы обращаетесь к var до того, как она была объявлена, она становится неопределенной. Но если вы сделаете то же самое для let и const, они выдадут ошибку ReferenceError.
```
console.log(varNumber); // undefined
console.log(letNumber); // Doesn't log, as it throws a ReferenceError letNumber is not defined

var varNumber = 1;
let letNumber = 1;
```
>Когда переменные подхватываются, var получает значение undefined, инициализированное по умолчанию в процессе подхвата. let и const также подхватываются, но не устанавливаются в значение undefined, когда они подхватываются. Let и const попадают в Temporal Dead Zone (временно мертвую зону).   
TDZ: термин для описания состояния - когда переменные недоступны. Они находятся в области видимости, но не объявлены. Переменные let и const существуют в TDZ с начала их объемлющей области видимости до момента их объявления.  

- ## Методы создания functions   
> 1. Function decloration
> 2. Function expression
> 3. Arrow function (стрелочная функция) - не имеет лексического окружения this. 
> 4. Immediately-Invoked Function Expressions (IIFE).   

> Стрелочные функции отличаются от обычных не только способом записи. Главное их отличие проявляется в том, как они работают с контекстом. Вкратце: контекст обычных функций зависит от места вызова, а контекст стрелочных функций — от того места, где они были определены.
```
const f1 = () => { // стрелочная функция
  console.log(this);
};
 
f1(); // undefined or window

function f2() { // обычная функция
  console.log(this);
}

f2(); // undefined or window

```
> Здесь поведение функций не отличается, так как контекстом вызова у обеих функций является сам модуль, а в es6 this у модулей не определен. Теперь попробуем добавить эти функции в объект:
```
const obj = {
  f1, f2,
};

obj.f1(); // undefined or window
obj.f2(); // { f1: [Function: f1], f2: [Function: f2] }
```

# JavaScript:

- ## Basics

  - [Data types](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures)
  - Number methods
  - String methods
  - let var const - differences
  - ternary operator
  - switch case - examples, where it can be useful
  - type conversions

- ## Advanced Expressions

  - Be able to discover cases of implicit data types conversion into boolean, string, number
  - Strict comparison
  - `Object.is` `(optional)`
  - what is polyfills

- ## Function

  - arrow func/ func expression/ func declaration

- ## Date & time `(optional)`

  - Date object
  - Date methods, props

- ## Objects Built-in methods.

  - Know how to use built-in methods

- ## Arrays Built-in methods

  - Know how to copy array
  - Know how to modify array

- ## Arrays Iterating, Sorting, Filtering

  - Know how to sort Array
  - Know several method how to iterate Array elements

- ## Loops

  - for loop
  - while loop
  - do while loop

#JavaScript in Browser:

- ## Global object window

  - Document

- ## Events Basics

  - Event Phases
  - Event Listeners
  - DOM Events
  - Know basic Event types
  - Mouse / Keyboard Events
  - Form / Input Events

- ## Timers

  - `setTimeout`
  - `setInterval`

- ## Web Storage API & cookies

  - LocalStorage
  - SessionStorage

