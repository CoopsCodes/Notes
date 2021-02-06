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
