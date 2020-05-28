# Webinar z JavaScript: Programowanie Obiektowe - snippety

## Obiekt tworzony przy pomocy literału

```
const kowalski = {
    firstName: 'Jan',
    lastName: 'Kowalski',
    getFullName: function() {
        return `${this.firstName} ${this.lastName}`;
    }
}
```

## Konstruktor - funkcja do tworzenia obiektów

```
function Person(firstNameVal, lastNameVal) {
    // this = {}
    // this.__proto__ = Person.prototype
    this.firstName = firstNameVal;
    this.lastName = lastNameVal;

    // return this;
}
```

## prototype - definiowanie metody dla obiektu tworzonego za pomocą konstruktora Person

```
Person.prototype.getFullName = function() {
    return `${this.firstName} ${this.lastName}`;
}
```

## class - nowy sposób (ES6) tworzenia obiektów w JS

```
class Person {
    constructor(firstNameVal, lastNameVal) {
        this.firstName = firstNameVal;
        this.lastName = lastNameVal;
    }

    getFullName() {
        return `${this.firstName} ${this.lastName}`;
    }
}
```

## extends - ponowne wykorzystanie kodu (dziedziczenie)

```
class Programmer extends Person {
    constructor(firstNameVal, lastNameVal, nickVal) {
        super(firstNameVal, lastNameVal);
        this.nick = nickVal;
    }

    getFullName() {
        return super.getFullName() + ' aka ' + this.nick;
    }
}

const jser = new Programmer('Michał', 'Koder', 'jser');
console.log( jser.getFullName() );
```
