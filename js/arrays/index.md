---
title: "Массив"
authors:
  - nlopin
contributors:
  - furtivite
tags:
  - doka
---

## Кратко

Массив — это структура, в которой можно хранить коллекции элементов — чисел, строк, других массивов и т.д. Элементы нумеруются и хранятся в том порядке, в котором их поместили в массив. Элементов может быть сколько угодно, они могут быть какими угодно.

Массивы очень похожи на нумерованные списки.

## Как пишется

Создадим массив с помощью квадратных скобок `[]`.

К примеру, можно создать пустой массив:

```js
const guestList = [] // 😭 гостей нет
```

А можно создать сразу с элементами внутри:

```js
const theGirlList = ['Серсея', 'Илин Пейн', 'Меррин Трант', 'Дансен', 'Гора']
```

Элементы могут быть разных типов:

```js
const infoArray = ['Россия', 'Москва', 144.5, 'Russian ruble', true]

// внутри массива могут быть другие массивы:
const arrayOfArrays = [
  'Россия',
  ['Москва', 'Санкт-Петербург', 'Казань', 'Екатеринбург'],
  [true, true, false, true]
]
```

## Как это понять

Массивы хранят элементы в пронумерованных «ячейках». Нумерация начинается с нуля. Первый элемент массива будет иметь номер 0, второй — 1 и так далее. Номера называют _индексами_.

Количество доступных ячеек называют _размером_ или _длиной_ массива. В JavaScript длина массива обычно совпадает с количеством элементов в нем. Массивы хранят свой размер в свойстве `length`:

```js
const infoArray = ['Россия', 'Москва', 144.5, 'Russian ruble', true]
console.log(infoArray.length)
// 5
```

### 💡 Чтение

Обратись к конкретному индексу, чтобы получить содержимое ячейки с этим номером. Если ячейка пустая или такой ячейки нет, то JavaScript вернёт `undefined`:

```js
const guestList = ['Маша', 'Леонард', 'Шелдон', 'Джон Сноу']

const firstGuest = guestList[0]
console.log(firstGuest)
// Маша

console.log(guestList[3])
// Джон Сноу

console.log(guestList[999])
// undefined
```

### 💡 Запись

Используй комбинацию чтения и оператора присваивания:

```js
const episodesPerSeasons = [10, 10, 10, 10, 10, 9, 7, 6]

console.log(episodesPerSeasons[5])
// 9

// запись в ячейку с индексом 5:
episodesPerSeasons[5] = 10
console.log(episodesPerSeasons[5])
// 10
```

### 💡 Добавление элементов

Частая операция. Используй методы:

- `push` — для добавления в конец массива
- `unshift` — для добавления в начало массива

Лучше использовать `push`, он работает быстрее. Оба принимают произвольное количество аргументов. Все аргументы будут добавлены в массив. Методы возвращают размер массива после вставки:

```js
const watched = ['Властелин Колец', 'Гарри Поттер']

// добавляем в конец
watched.push('Зеленая Книга')
console.log(watched)
// ['Властелин Колец', 'Гарри Поттер', 'Зеленая книга']

let newLength = watched.push('Мстители', 'Король Лев')
console.log(newLength)
// 5

// добавляем в начало
newLength = watched.unshift('Грязные танцы')
console.log(newLength)
// 6
console.log(watched)
// ['Грязные танцы', 'Властелин Колец', 'Гарри Поттер', 'Зеленая книга', 'Мстители', "Король Лев']
```

### 💡 Создать большой массив из чисел

С помощью цикла и метода `push` можно быстро создать большой массив с числами.

Создадим массив чисел от 1 до 1000:

```js
const numbers = []
for (let i = 1; i <= 1000; ++i) {
  numbers.push(i)
}
```

Создадим массив чётных чисел от 0 до 1000:

```js
const evenNumbers = []
for (let i = 0; i <= 1000; i += 2) {
  evenNumbers.push(i)
}
```

### 💡 Поиск по массиву

Используй [`indexOf`](/js/index-of/), чтобы найти, под каким индексом хранится элемент.

Используйте [`includes`](/js/includes/), чтобы проверить, что элемент есть в массиве:

```js
const episodesPerSeasons = [10, 10, 10, 10, 10, 9, 7, 6]

console.log(episodesPerSeasons.includes(8))
// false
console.log(episodesPerSeasons.includes(6))
// true
```
