---
title: Синтаксис YAML
---

YAML (YAML Ain't Markup) является дружественным человеческим языком специализации данных.

Flextype использует YAML, потому что он так близок к простому английскому языку, как специализация данных и конфигурация форматов получить. Он не имеет фигурных скобок, в большинстве случаев позволяет опустить кавычки для строк, а для структуры полагается на отступ, что делает его невероятно читаемым по сравнению с другими языками, такими как JSON и XML.

YAML широко используется в Flextype для конфигурационных файлов, наборов полей, а также в настройках записей.

### Основные правила

Существуют некоторые правила, которые существуют в YAML, чтобы избежать вопросов, связанных с двусмысленностью в отношении различных языков и редактирования программ. Эти правила позволяют последовательно интерпретировать один файл YAML независимо от того, какое приложение или библиотека используется для его интерпретации.

* YAML-файлы должны заканчиваться на .yaml, по возможности в Flextype.
* YAML чувствительна к регистру.
* YAML не позволяет использовать вкладки. Вместо этого используются пробелы, так как вкладки не всегда поддерживаются.

### Тип данных

Значения в парах ключ-значение YAML являются скалярными. Они действуют как скалярные типы в языках Perl, Javascript и Python. Обычно достаточно хорошо заключать строки в кавычки, оставлять цифры без кавычек и позволять парсеру разобраться в них.

Но это только верхушка айсберга. YAML способен на гораздо большее.

#### Пары ключевых слов и словари ключевых значений

Ключевое значение является основным структурным элементом YAML. Каждый пункт в документе YAML является членом хотя бы одного словаря. Ключом всегда является строка. Значение является скалярным и может быть любым типом данных.

Итак, как мы уже видели, значением может быть строка, число или другой словарь.

#### Числовые типы

YAML распознает числовые типы. Мы в идем двоеточие и целые числа ниже. YAML поддерживает несколько других цифровых типов.

```
foo: 12345
bar: 0x12d4
```

#### Строки

YAML строки - это Unicode. В большинстве случаев, вам не нужно указывать их в кавычках.

```
foo: this is a normal string
```

Если мы хотим работать с управляющими последовательностями, нам нужно использовать двойные кавычки.

```
foo: "this is not a normal string\n"
bar: this is not a normal string\n
```

YAML обрабатывает первое значение как заканчивающееся возвратом и подачей строки. Поскольку второе значение не цитируется, YAML рассматривает `\n` как два символа.

YAML не будет экранировать строки с одиночными кавычками, но одиночные кавычки не будут иметь содержимое строк, интерпретируемое как форматирование документа.

Строковые значения могут охватывать более одной строки. С помощью символа складки (больше) можно указать строку в блоке. Но это интерпретируется без новых строк.

```
foo: >
  this is not a normal string it
  spans more than
  one line
  see?
```

Символ блока (pipe) имеет схожую функцию, но YAML интерпретирует поле точно так же, как есть. Итак, мы видим в документе новые строки, где они находятся.

```
foo: |
  this is not a normal string it
  spans more than
  one line
  see?
```


#### Недействительный

Вы вводите нули с тильдой или цитируемым нулевым строковым литералом.

```
foo: ~
bar: null
```

#### Логические значения

YAML указывает логические значения с ключевыми словами True, On и Yes для true. False обозначается как False, Off или No.

```
foo: True
bar: False
light: On
TV: Off
```

#### Массивы

Вы можете указать массивы или списки в одной строке.

```
items: [ 1, 2, 3, 4, 5 ]
names: [ "one", "two", "three", "four" ]
```

Или вы можете поставить их на несколько строк.

```
items:
  - 1
  - 2
  - 3
  - 4
  - 5
names:
  - "one"
  - "two"
  - "three"
  - "four"
```

Многострочный формат полезен для списков, содержащих сложные объекты, а не скаляры.

```
items:
  - things:
      thing1: huey
      things2: dewey
      thing3: louie
  - other things:
      key: value
```

Массив может содержать любое допустимое значение YAML. Значения в списке не обязательно должны быть одного и того же типа.

#### Словари

Мы рассмотрели словари выше, но есть еще кое-что.

Как и массивы, вы можете добавлять словари в последовательность. Мы видели этот формат выше. Это как python печатает словари.

```
foo: { thing1: huey, thing2: louie, thing3: dewey }
```

### Ресурсы и дальнейшая документация

* [Официальная документация YAML 1.2](https://yaml.org/spec/1.2/spec.html)
* [Справочная карта YAML](https://yaml.org/refcard.html)
* [YAML Lint](http://www.yamllint.com)