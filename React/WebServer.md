# Setting up a Web Server

A **Web Server** is used to preview te project in the browser, but also to constantly _watch_ for changes in the project folder and update the site as you build.

In the project root create a Public folder containing the index.html file used as the entry point to the project.

Set that html file up with default

```
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title>Title Here</title>
	</head>
	<body>
		Test
	</body>
</html>
```

Install **Live-Server** with yarn

```
	$ yarn global add live-server
```

Or Install **Live-Server** with NPM

```
	$ npm install -g live-server
```

Check that **Live-Server** has installed properly by running a version check

```
	$ live server -v
```

This should display live server and a version number. This should generally be run after every install to ensure there haven't been any install issues.

Then you're good to run live-server, First

**MAKE SURE YOUR COMMAND LINE IS POINTING TO THE CORRECT FOLDER**

i.e the folder above public in this case. and run the following command

```
	live-server public
```

This will locate the html file and run it and will open the web browser, and you should see the text you wrote in the HTML file on the page.
