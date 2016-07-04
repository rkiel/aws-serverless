

# JavaScript

### Variables and Literals

#### Strings

```javascript
var firstName = 'Terry';
var lastName = 'Brown';
```

#### Numbers

```javascript
var age = 40;
var pi = 3.14;
```

#### Falsy

* `false`
* `null`
* `undefined`
* `''`  // empty string
* `0`

#### Truthy

* `true`
* `'true'`
* `'false'`
* all other non-falsy values

#### Array

```javascript
var rush = ['Geddy','Alex','Neil'];
```

#### Object

```javascript
{
  firstName: 'Terry',
  lastName: 'Brown',
  age: 40
}
```
##### Assigning a Literal

```javascript
var person = {
  firstName: 'Terry',
  lastName: 'Brown',
  age: 40
};
```

##### Accessing as a property and as a hash map

```javascript
person.firstName // Terry
person['firstName'] // Terry
```

##### Assigning as a property and as a hash map

```javascript
person.fullName = persons.firstName + ' ' + person.lastName;
person.['fullName'] = persons.firstName + ' ' + person.lastName;
```

### Functions

#### Defining and invoking

```javascript
function square(x) {
  return x * x;
}

square(5); // 25
```

#### Defining and assigning

```javascript
var square = function(x) {
  return x * x;
}

square(5); // 25
```

#### Passing

```javascript
function square(x) {
  return x * x;
}

function cube(x) {
  return x * x * x;
}

function calculate(f, x) {
  return f(x);
}

calculate(square, 5); // 25
calculate(cube, 3); // 27
```
