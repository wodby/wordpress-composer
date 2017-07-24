# Composer template for WordPress projects

This project template should provide a kickstart for managing your site dependencies with [Composer](https://getcomposer.org/).

This project consist of:

* WordPress core: https://github.com/johnpbloch/wordpress-core-installer and https://github.com/johnpbloch/wordpress-core  
* WordPress plugins and themes by https://wpackagist.org/. See composer.json file to learn how to install plugins and themes
* `wodby.yml` that runs `composer install`. You can remove it if you're not using [Wodby](https://wodby.com)

By default, wordpress core will be installed in `./web` directory. Plugins and themes are installed in `./web/wp-content/plugins` and `./web/wp-content/themes`.

## Usage

* First you need to [install composer](https://getcomposer.org/doc/00-intro.md#installation-linux-unix-osx)
* Fork this repository
* Run composer install

## Using with [Wodby](https://wodby.com)

* Fork this repository
* Connect the repository to Wodby
* Deploy new app, choose WordPress stack, on the 2nd step of the form choose connected repository and enter `web` as Codebase dir 
