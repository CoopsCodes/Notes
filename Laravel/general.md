# Blade

Welcome y'all. Here goes with my introduction to Laravel and PHP

Blade is a templating engine, so say we want to point to a template we create a standard HTML file

```html
location: resources/views/layouts/app.blades.php
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8" />
		<meta name="viewport" content="width=device-width, initial-scale=1.0" />
		<meta http-equiv="X-UA-Compatible" content="ie=edge" />
		<title>Title</title>
	</head>
	<body>
		@yield('content')
	</body>
</html>
```

The most important part here is the `@yield('content')` tag, this is the injection point for the templates we're about to produce.

## Blade Directives

OK, so we have our injection point, what next.

We use Blade Directives to generate the content in the `@yield('')`

```
location: resources/views/posts/index.blades.php

	@extends('layout.app')

	@section('content')

	@endsection
```

@extends: points to the directory, PHP uses dot notation rather than slash. this points to the layouts folder and the app file.

@section: points to the '@yield('content')' location in the file described above

@endsection: Indicates the end of the template

## Views

So what if we want to see the posts, well we use the Routes directory to send all our pages to the correct place.

```
location: routes/web.php

Route::get('/', function () {
    return view('posts.index');
});
```

This will probably make sense to a lot of people, especially if you've used Routes.

This returns the view in the posts.index location.

## Running the app

If adding any JS dependencies (i.e tailwind) run the `npm install` command as this will generate the app by bundling in all the dependencies that are required in the app.

That will create the `package.json` file and create the `"dev": "npm run development"` script that we can then use to kick off the local dev server.
