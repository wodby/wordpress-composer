# Composer Template for WordPress Projects

This project template should provide a kickstart for managing your site dependencies with [Composer](https://getcomposer.org/).

This project consist of:

* WordPress core: [johnpbloch/wordpress-core-installer](https://github.com/johnpbloch/wordpress-core-installer)
* Repository https://wpackagist.org/ to install WordPress plugins and themes
* `composer/installers` to set custom paths for plugins and themes
* `drupal-composer/preserve-paths` to exclude paths for plugins and themes under version control 
* `wodby.yml` that runs `composer install`. You can remove it if you're not using [Wodby](https://wodby.com)

Current WordPress core: `~4.9`

### Paths

By default, wordpress core will be installed in `./web` directory. Plugins and themes are installed in `./web/wp-content/plugins` and `./web/wp-content/themes`.

### Usage

1. First you need to [install composer](https://getcomposer.org/doc/00-intro.md#installation-linux-unix-osx)
2. Fork and clone this repository
3. Run composer install in your repository root

### How to install WordPress plugins and themes?

Update `require` section in `composer.json` as described on https://wpackagist.org/ 

### How to manage my custom themes and plugins under version control?

1. Exclude path to your plugin or theme from .gitignore. Example for theme under `web/wp-content/themes/my-custom-theme/`:
    ```
    !web/
    web/*
    !web/wp-content/
    web/wp-content/*
    !web/wp-content/themes/
    web/wp-content/themes/*
    !web/wp-content/themes/my-custom-theme/
    ``` 
2. Add the same path to your composer.json under `extra > preserve-paths`: 
    ```
    "preserve-paths": [
      "web/wp-content/themes/custom"
    ]
    ```
3. Add your plugin/theme directory under version control
4. Run `composer install`. Composer will install WordPress core and keep your custom theme

### Deployment via Wodby

1. Fork this repository
2. Connect the repository to Wodby
3. Deploy new app, choose WordPress stack, on the 2nd step of the form choose connected repository and enter `web` as Codebase dir 