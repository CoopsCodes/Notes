# Javascript

## ES6 Arrow functions

```
	<!-- The old way -->
	function square(x) {
		return x * x
	};
```

The ES6 way

```
	const square = (x) => {
		return x * x
	};
```

If the function is simple it can be simplified

```
	const square = (x) => x * x;
```

## Classes

A JavaScript Class template

```
class Person = {
	constructor(name = "default if not passed in", age = 0) {
		this.name = name,
		this.age = age
	}
	greeting() {
		return `Hi my name is ${this.name}! and I'm ${this.age}`
	}
}

const me = new Person("Cooper Viktor", 35, "Stuff")

```

A SubClass is a class that inherits from a parent class, i.e Student is a Person too but needs extra fields.
This utilises the **extends** keyword.

To inherit the constructor functions we must pass those through the super() method

```
class Student extends Person = {
	constructor(name, age, major) {
		super(name, age)
		this.major = major
	}
	hasMajor() {
		!!this.major
	}
	greeting() {
		let description = super.greeting();
		if(hasMajor()) {
			description += ` and they studied ${this.major}`
		}
		return description;
	}
}
const me = new Person("Cooper Viktor", 35, "Stuff");
console.log(me.greeting());
```

if a method in a subclass is given the same name as a parent class, it overrides it. unless the subclass method invokes the parent via super and modifies it in some way
