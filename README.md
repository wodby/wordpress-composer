# Composer template for WordPress projects

This project template should provide a kickstart for managing your site dependencies with [Composer](https://getcomposer.org/).

This project consist of:

* WordPress core: [johnpbloch/wordpress-core-installer](https://github.com/johnpbloch/wordpress-core-installer)
* Repository https://wpackagist.org/ to install WordPress plugins and themes
* `wodby.yml` that runs `composer install`. You can remove it if you're not using [Wodby](https://wodby.com)

### Paths

By default, wordpress core will be installed in `./web` directory. Plugins and themes are installed in `./web/wp-content/plugins` and `./web/wp-content/themes`.

### How to install WordPress plugins and themes

Use [`composer require`](https://getcomposer.org/doc/03-cli.md#require) or update composer.json as described on https://wpackagist.org/ 

### Usage

* First you need to [install composer](https://getcomposer.org/doc/00-intro.md#installation-linux-unix-osx)
* Fork this repository
* Run composer install

### Using with Wodby

* Fork this repository
* Connect the repository to Wodby
* Deploy new app, choose WordPress stack, on the 2nd step of the form choose connected repository and enter `web` as Codebase dir 
