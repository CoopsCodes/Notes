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
	constructor(name = "default if not passed in", age) {
		this.name = name,
		this.age = age
	}
	greeting() {
		return `Hi my name is ${this.name}! and I'm ${this.age}`
	}
}
const me = new Person("Cooper Viktor", 35)

```
