
# GitHub Web Sample



[GitHub Web Sample] is simple HTML and CSS web application that talk a little Lorem ipsum. The web application is not adaptive, not reponsible but a simple HTML Doc tags for our GitHub Tutorial Sample.



## Table of content

- [Supported versions](#supported-versions)
- [Basic application](#basic-application)
- [Installation](#installation)
- [License](#license)
- [Links](#links)


## Supported versions

This document is for the Aimeos Laravel package **2020.10 and later**.

- LTS release: 2020.10 (6.x, 7.x and 8.x)
- Old LTS release: 2019.10 (Laravel 5.5+, 6.x and 7.x)

If you want to **upgrade between major versions**, please have a look into the
[upgrade guide](https://aimeos.org/docs/latest/laravel/setup/#upgrade)!

## Basic application

### Full shop application

If you want to set up a new application or test Aimeos, we recommend the
[Aimeos shop application](https://github.com/aimeos/aimeos). It will install a
complete shop system using the **last LTS version** including demo data for a quick
start without the need to follow the steps described in this readme:

```
composer create-project aimeos/aimeos myshop
```

More about the full package: :star: [Aimeos shop](https://github.com/aimeos/aimeos)



## Installation

### How To Run The Project
1. First Download this project in ZIP format.
1. On your default download folder, extract the file
1. After extracting, open the folder
1. In the folder, double click the index.html file
1. Depending on your default browser, it should display the web application.

Thanks For Using our code.





## Usage

### How To Edit The content
1. To add or modify the web app content, open the project folder with a text editor
![Editing] (5 (2).png)
Format: ![Alt Text](5 (2).png)
1. Then continue with adding a file to the project
1. Or to edit, Right click the the file you like to modify on the text editor
1. This will open the file content at right pane of the editor
1. Then apply your changes

Thanks




## Setup

To see all components and get everything working, you also need to create your
main Blade template in `resources/views/app.blade.php`. This is a working
example using the [Twitter bootstrap CSS framework](http://getbootstrap.com/):

```html
<!DOCTYPE html>
<html lang="en" class="no-js">
<head>
	<meta charset="utf-8">
	<meta http-equiv="X-UA-Compatible" content="IE=edge">
	<meta name="viewport" content="width=device-width, initial-scale=1">
	@yield('aimeos_header')
	<title>Aimeos on Laravel</title>
	<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@4/dist/css/bootstrap.min.css">
	<style>
		/* Theme: Black&White */
		/* body {
			--ai-primary: #000; --ai-primary-light: #000; --ai-primary-alt: #fff;
			--ai-bg: #fff; --ai-bg-light: #fff; --ai-bg-alt: #000;
			--ai-secondary: #555; --ai-light: #D0D0D0;
		} */
		body { color: #000; color: var(--ai-primary, #000); background-color: #fff; background-color: var(--ai-bg, #fff); }
		.navbar, footer { color: #555; color: var(--ai-primary-alt, #555); background-color: #f8f8f8; background-color: var(--ai-bg-alt, #f8f8f8); }
		.navbar a, .navbar a:before, .navbar span, footer a { color: #555 !important; color: var(--ai-primary-alt, #555) !important; }
		.content { margin: 0 5% } .catalog-stage-image { margin: 0 -5.55% }
		.sm { display: block } .sm:before { font: normal normal normal 14px/1 FontAwesome; padding: 0 0.2em; font-size: 225% }
		.facebook:before { content: "\f082" } .twitter:before { content: "\f081" } .instagram:before { content: "\f16d" } .youtube:before { content: "\f167" }
	</style>
	@yield('aimeos_styles')
</head>
<body>
	<nav class="navbar navbar-expand-md navbar-light">
		<a class="navbar-brand" href="/">
			<img src="http://aimeos.org/fileadmin/template/icons/logo.png" height="30" title="Aimeos Logo">
		</a>
		<button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
			<span class="navbar-toggler-icon"></span>
		</button>
		<div class="collapse navbar-collapse justify-content-end" id="navbarNav">
			<ul class="navbar-nav">
				@if (Auth::guest())
					<li class="nav-item"><a class="nav-link" href="/login">Login</a></li>
					<li class="nav-item"><a class="nav-link" href="/register">Register</a></li>
				@else
					<li class="nav-item dropdown">
						<a href="#" class="nav-link dropdown-toggle" data-toggle="dropdown" role="button" aria-expanded="false">{{ Auth::user()->name }} <span class="caret"></span></a>
						<ul class="dropdown-menu" role="menu">
							<li><a class="nav-link" href="{{ route('aimeos_shop_account',['site'=>Route::current()->parameter('site','default'),'locale'=>Route::current()->parameter('locale','en'),'currency'=>Route::current()->parameter('currency','EUR')]) }}" title="Profile">Profile</a></li>
							<li><form id="logout" action="/logout" method="POST">{{csrf_field()}}</form><a class="nav-link" href="javascript: document.getElementById('logout').submit();">Logout</a></li>
						</ul>
					</li>
				@endif
			</ul>
			@yield('aimeos_head')
		</div>
	</nav>
	<div class="content">
		@yield('aimeos_stage')
		@yield('aimeos_nav')
		@yield('aimeos_body')
		@yield('aimeos_aside')
		@yield('content')
	</div>
	<footer class="mt-5 p-5">
		<div class="row">
			<div class="col-md-8">
				<div class="row">
					<div class="col-sm-6 my-4"><h2 class="pb-3">LEGAL</h2><p><a href="#">Terms & Conditions</a></p><p><a href="#">Privacy Notice</a></p><p><a href="#">Imprint</a></p></div>
					<div class="col-sm-6 my-4"><h2 class="pb-3">ABOUT US</h2><p><a href="#">Contact us</a></p><p><a href="#">Company</a></p></div>
				</div>
			</div>
			<div class="col-md-4 my-4">
				<a class="px-2 py-4 d-inline-block" href="/"><img src="http://aimeos.org/fileadmin/template/icons/logo.png" style="width: 160px" title="Aimeos Logo"></a>
				<div class="social"><a href="#" class="sm facebook" title="Facebook" rel="noopener">Facebook</a><a href="#" class="sm twitter" title="Twitter" rel="noopener">Twitter</a><a href="#" class="sm instagram" title="Instagram" rel="noopener">Instagram</a><a href="#" class="sm youtube" title="Youtube" rel="noopener">Youtube</a></div>
			</div>
		</div>
	</footer>
	<!-- Scripts -->
	<script src="https://cdn.jsdelivr.net/combine/npm/jquery@3,npm/bootstrap@4"></script>
	@yield('aimeos_scripts')
	</body>
</html>
```

Afterwards, you should clear the Laravel cache files. Otherwise, you might get
an exception due to old cached data.

```php artisan cache:clear```

To reference images correctly, you have to adapt your `.env` file and set the `APP_URL`
to your real URL, e.g.

```APP_URL=http://127.0.0.1:8000```

**Caution:** Make sure, Laravel uses the `file` session driver in your `.env` file!
Otherwise, the shopping basket content won't get stored correctly!

```SESSION_DRIVER=file```

Then, you should be able to call the catalog list page in your browser. For a
quick start, you can use the integrated web server that is available since PHP 5.4.
Simply execute this command in the base directory of your application:

```php artisan serve```

Point your browser to the list page of the shop using:

http://127.0.0.1:8000/index.php/shop

**Note:** Integrating the Aimeos package adds some routes like `/shop` or `/admin` to your
Laravel installation but the **home page stays untouched!** If you want to add Aimeos to
the home page as well, replace the route for "/" in `./routes/web.php` by this line:

```
Route::get('/', '\Aimeos\Shop\Controller\CatalogController@homeAction')->name('aimeos_home');
```

This will display the Aimeos catalog home component on the home page you you get a
nice looking shop home page. The `/shop` page will look like:

[![Aimeos frontend](https://aimeos.org/fileadmin/aimeos.org/images/aimeos-frontend.png)](http://127.0.0.1:8000/index.php/shop)

## Admin

To use the admin interface, you have to set up Laravel authentication first:

### Laravel 8

```
composer require laravel/jetstream
php artisan jetstream:install livewire
npm install && npm run dev
```

For more information, please follow the Laravel documentation:
* [Laravel 8.x](https://laravel.com/docs/8.x/authentication)

### Laravel 7

```
composer require laravel/ui:^2.0
php artisan ui vue --auth
npm install && npm run dev
```

For more information, please follow the Laravel documentation:
* [Laravel 7.x](https://laravel.com/docs/7.x/authentication)

### Laravel 6

```
composer require laravel/ui:^1.0
php artisan ui vue --auth
npm install && npm run dev
```

For more information, please follow the Laravel documentation:
* [Laravel 6.x](https://laravel.com/docs/6.x/authentication)

### Laravel 5.x

```php artisan make:auth```

For more information, please follow the Laravel documentation:
* [Laravel 5.8](https://laravel.com/docs/5.8/authentication)
* [Laravel 5.7](https://laravel.com/docs/5.7/authentication)
* [Laravel 5.6](https://laravel.com/docs/5.6/authentication)
* [Laravel 5.5](https://laravel.com/docs/5.5/authentication)

### Create account

Test if your authentication setup works before you continue. Create an admin account
for your Laravel application so you will be able to log into the Aimeos admin interface:

```php artisan aimeos:account --super <email>```

The e-mail address is the user name for login and the account will work for the
frontend too. To protect the new account, the command will ask you for a password.
The same command can create limited accounts by using "--admin", "--editor" or "--api"
instead of "--super" (access to everything).

### Configure authentication

As a last step, you need to extend the `boot()` method of your
`App\Providers\AuthServiceProvider` class and add the lines to define how
authorization for "admin" is checked in `app/Providers/AuthServiceProvider.php`:

```php
    public function boot()
    {
        // Keep the lines before

        Gate::define('admin', function($user, $class, $roles) {
            if( isset( $user->superuser ) && $user->superuser ) {
                return true;
            }
            return app( '\Aimeos\Shop\Base\Support' )->checkUserGroup( $user, $roles );
        });
    }
```

### Test

If your `./public` directory isn't writable by your web server, you have to create these
directories:
```
mkdir public/files public/preview public/uploads
chmod 777 public/files public/preview public/uploads
```

In a production environment, you should be more specific about the granted permissions!
If you've still started the internal PHP web server (`php artisan serve`)
you should now open this URL in your browser:

http://127.0.0.1:8000/index.php/admin

Enter the e-mail address and the password of the newly created user and press "Login".
If you don't get redirected to the admin interface (that depends on the authentication
code you've created according to the Laravel documentation), point your browser to the
`/admin` URL again.

**Caution:** Make sure that you aren't already logged in as a non-admin user! In this
case, login won't work because Laravel requires to log out first.

[![Aimeos backend](https://aimeos.org/fileadmin/aimeos.org/images/aimeos-backend.png)](http://127.0.0.1:8000/index.php/admin)

## Hints

To simplify development, you should configure to use no content cache. You can
do this in the `config/shop.php` file of your Laravel application by adding
these lines at the bottom:

```php
    'madmin' => array(
        'cache' => array(
            'manager' => array(
                'name' => 'None',
            ),
        ),
    ),
```

## License

The Aimeos Laravel package is licensed under the terms of the MIT license and
is available for free.

## Links

* [Web site](https://aimeos.org/Laravel)
* [Documentation](https://aimeos.org/docs/Laravel)
* [Forum](https://aimeos.org/help/laravel-package-f18/)
* [Issue tracker](https://github.com/aimeos/aimeos-laravel/issues)
* [Composer packages](https://packagist.org/packages/aimeos/aimeos-laravel)
* [Source code](https://github.com/aimeos/aimeos-laravel)
