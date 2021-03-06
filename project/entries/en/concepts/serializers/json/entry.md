---
title: JSON
description: Flextype uses YAML because it's as close to plain English as data serialization and configuration formats get. It has no curly braces, it allows you to omit quotation marks for strings in most cases, and it relies on indentation for structure, which makes it incredibly readable compared to other languages, such as JSON and XML.
breadcrumbs:
  0:
    title: "Documentation"
    link: "[url]/en/"
  1:
    title: "Concents"
    link: "[url]/en/concepts/"
  2:
    title: "Serializers"
    link: "[url]/en/concepts/serializers/"
on_this_page:
  0:
    title: "JSON Syntax"
    link: "json-syntax"
  1:
    title: "JSON Data Types"
    link: "json-data-types"
---

JSON (JavaScript Object Notation) is most widely used data format for data interchange on the web. This data interchange can happen between two computers applications at different geographical locations or running within same hardware machine.

The good thing is that JSON is a human and machine readable format. So while applications/libraries can parse the JSON data – humans can also look at data and derive meaning from it.

A JSON document may contains text, curly braces, square brackets, colons, commas, double quotes, and maybe a few other characters.

Primarily, JSON is built on two structures:

* A collection of name/value pairs. In various languages, this is realized as an object, record, struct, dictionary, hash table, keyed list, or associative array.
* An ordered list of values. In most languages, this is realized as an array, vector, list, or sequence.

We are using JSON sytnax in our [Content APIs]([url]/concepts/content-apis).

### <a name="json-syntax"></a> JSON Syntax

A JSON document may contain information separated by following separators/token.

* `:` to separate name from value
* `,` to separate name-value pairs
* `{` and `}` for objects
* `[` and `]` for arrays

### JSON name-value pairs example

Name-value pairs have a colon between them as in **name** : **value**.

JSON names are on the left side of the colon. They need to be wrapped in double quotation marks, as in **name**, and can be any valid string. Within each object, keys need to be unique.

JSON values are found to the right of the colon. At the granular level, these need to be one of 6 simple data types:

* strings
* numbers
* objects
* arrays
* booleans
* null or empty

Each name-value pair is separated by a comma, so the JSON looks like this:

```
"name" : "value", "name" : "value", "name": "value"
```

```
{
  "color" : "Purple",
  "id" : "210"
}
```

### JSON object example

A JSON object is a key-value data format that is typically rendered in curly braces. A JSON object looks something like this:

```
{
  "color" : "Purple",
  "id" : "210",
  "composition" : {
    "R" : 70,
    "G" : 39,
    "B" : 89
  }
}
```

### JSON array example

Data can also be nested within the JSON by using JavaScript arrays that are passed as a value using square brackets [ ] on either end of its array type.

JSON arrays are ordered collections and can contain values of differing data types.

```
{
    "colors" :
    [
        {
          "color" : "Purple",
          "id" : "210"
        },
        {
          "color" : "Blue",
          "id" : "211"
        },
        {
          "color" : "Black",
          "id" : "212"
        }
    ]
}
```

### <a name="json-data-types"></a> JSON Data Types

JSON consist of 6 data types. First four data types (string, number, boolean and null) can be referred as simple data types. Other two data types (object and array) can be referred as complex data types.

* string
* number
* boolean
* null/empty
* object
* array

<table>
    <tr>
        <td><b>Data Type</b></td>
        <td><b>Description</b></td>
    </tr>
    <tr>
        <td><code>string</code></td>
        <td>
        Strings in JSON must be written in double quotes. <br><br>
<pre><code class="hljs">{
  "color" : "Purple"
}
</code></pre>
        </td>
    </tr>
    <tr>
        <td><code>number</code></td>
        <td>
        Numbers in JSON must be an integer or a floating point. <br><br>
<pre><code class="hljs">{
  "number_1": 210,
  "number_2": -210,
  "number_3": 21.05,
  "number_4": 1.0E+2
}
</code></pre>
        </td>
    </tr>
    <tr>
        <td><code>boolean</code></td>
        <td>
        Value can be either true or false. <br><br>
<pre><code class="hljs">{
  "visibility": true
}
</code></pre>
        </td>
    </tr>
    <tr>
        <td><code>null</code></td>
        <td>
        Values in JSON can be null. <br><br>
<pre><code class="hljs">{
   "middlename": null
}
</code></pre>
        </td>
    </tr>
    <tr>
        <td><code>object</code></td>
        <td>
        Values in JSON can be objects. <br><br>
<pre><code class="hljs">"employee": {
  "name": "John",
  "age": 30,
  "city": "New York"
}
</code></pre>
        </td>
    </tr>
    <tr>
        <td><code>array</code></td>
        <td>
        Values in JSON can be arrays. <br><br>
<pre><code class="hljs">{
  "employees": [ "John", "Anna", "Peter" ]
}
</code></pre>
        </td>
    </tr>
</table>
