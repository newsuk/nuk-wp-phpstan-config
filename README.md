### NUK WP PHPStan config

This library contains PHPStan configuration for NewsUK plugins and themes.

## Installation

Composer install:

```bash
composer require --dev newsuk/nuk-wp-phpcstan-config
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
Add the following to `scripts` section in `composer.json` file to run code scan.

```json
"phpstan": "phpstan analyse --memory-limit=2048M",
```