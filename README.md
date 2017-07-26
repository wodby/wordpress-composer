# Composer template for WordPress projects

This project template should provide a kickstart for managing your site dependencies with [Composer](https://getcomposer.org/).

This project consist of:

* WordPress core: [johnpbloch/wordpress-core-installer](https://github.com/johnpbloch/wordpress-core-installer)
* Repository https://wpackagist.org/ to install WordPress plugins and themes
* `composer/installers` to set custom paths for plugins and themes
* `drupal-composer/preserve-paths` to exclude paths for plugins and themes under version control 
* `wodby.yml` that runs `composer install`. You can remove it if you're not using [Wodby](https://wodby.com)

### Paths

By default, wordpress core will be installed in `./web` directory. Plugins and themes are installed in `./web/wp-content/plugins` and `./web/wp-content/themes`.

### Usage

* First you need to [install composer](https://getcomposer.org/doc/00-intro.md#installation-linux-unix-osx)
* Fork this repository
* Run composer install

### Using with Wodby

* Fork this repository
* Connect the repository to Wodby
* Deploy new app, choose WordPress stack, on the 2nd step of the form choose connected repository and enter `web` as Codebase dir 

### How to install WordPress plugins and themes?

Update `require` section in `composer.json` as described on https://wpackagist.org/ 

### How to manage my custom themes and plugins under version control?

* Exclude path to your plugin or theme from .gitignore. Example for theme under `web/wp-content/themes/my-custom-theme/`:
```
!web/
web/*
!web/wp-content/
web/wp-content/*
!web/wp-content/themes/
web/wp-content/themes/*
!web/wp-content/themes/my-custom-theme/
``` 
* Add the following lines to your composer.json under `extra` (make sure it's before `wordpress-install-dir`): 
```
"preserve-paths": [
  "web/wp-content/themes/custom"
]
```
* Add your plugin/theme directory under version control
* Run `composer install`. Composer will install WordPress core and keep your custom theme