### NUK WP PHPStan config

This library contains PHPStan configuration for NewsUK plugins and themes.

## Installation

Composer install:

```bash
composer require --dev newsuk/nuk-wp-phpstan-config
```

## Using the ruleset
Create a `phpstan.neon.dist` file in your project and add the following:

```yml
parameters:
    level: max
    paths:
        # adjust the filename / directory name according to project needs.
        - plugin.php
        - includes/
```


## Composer scripts
Add the following to `scripts` section in `composer.json` file and run `composer phpstan`

```json
"phpstan": "phpstan analyse --memory-limit=2048M"
```
Add the following to generate baseline file for existing plugins and run `composer phpstan-baseline`

```json
"phpstan-baseline": "phpstan analyse -b --allow-empty-baseline"
```