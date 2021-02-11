To generate the CLI command line interface

```
	php artisan
```

Opening and closing PHP commands are wrapped in `<?php ?>` and statements must always be concluded with a semicolon, and comments are very similar.

```php
<?php
	// comments are like HTML
	# but they also use a hash
	/*
		multiple lines are the same
	*/
?>
```

# Strings

```php
<?php
	echo "Hello World";

	# Say we want to use quotation marks in a sting
	# they must be escaped before the inner quotation marks.
	echo "Hello \"World\""
	# by default the another echo would print on the same line as above, we can use escape characters to move to a new line
	echo "\n Welcome to the Jungle";

	# String Concatenation is done with a period
	echo "One String " . "Two String";

?>
```

# Variables

```php
<?php
	# Variables are assigned with a $
	$name = "Cooper";
	$language "PHP";

	# Variables can be concatenated within string

	echo "My name is $name and I am learning $language";
	echo "My name is ${name}'s and I am ${language}ing";
?>
```

```php
<?php
	# We can also concatenate variables with the same name together with a .= operator.
	$foo = "foo";
	$foo .= "bar";

	echo $foo; //=> "foobar"

	# Say we want to reassign a variable, this can be done with =& operator.
	# This will point the new variable to the same place in memory, rather than creating two memory locations.
	$variable_one = "Kentucky Fried Chicken";

	# Variable two is declared, but rather than creating a new variable
	# it renames and points to the variable one's location.
	$variable_two =& $variable_one;

	# But with some concatenation magic
	$variable_two .= " and a Pizza Hut";

	echo $variable_two; //=> Kentucky Fried Chicken and a Pizza Hut
?>
```

# Numbers

```php
<?php
	/*
		PHP has two number data types. The integer data type includes positive and negative whole numbers (such as 3, 4599, -98, and 0). The floating point data type is used to represent decimal numbers (such as 4.98273, 2.1, -9.7, -182736.8).
	*/

	# all the regular multipliers exist + - * /

	# Exponential operator is a double **
	echo 4 ** 2; //=> Prints: 16

	# on floats and negative numbers
	echo 2.89 ** 3.2;  //=> Prints: 29.845104015297
	echo 10 ** -1; //=> Prints: 0.1


?>
```
