# Getting Started

## Requirements
- written in PHP 8
- Docker, Apache or NGINX

## Installation

1. Download the latest release or git clone the repository
2. Move the content to `/var/www/html`

## Programming

### Creating your first controller

1. Create a new class in the `src/controllers` directory.
2. Let your class extend controller and add a function.
3. Let your function return something like `Hello World!`
4. Add your controller to the routes in `routes.php`

##### **`src/controllers/HelloWorldController.php`**

```php
<?php

class HelloWorldController implements IController 
{
	public function world()
	{
		return  'Hello World!';
	}
}
```

### Registering a controller as route

##### **`routes.php`**

```php
<?php

$routes = [
	...

	'/'  => [HelloWorldController::class, 'world'],

	...
];

```

This will execute the `world` function in the `HelloWorldController` at `/`.

#### Testing the Route
```
user@box:/var/www/html$ curl http://localhost/
Hello World!
```