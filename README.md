# nuk-wp-phpstan-config

This library contains PHPStan configuration for NewsUK plugins and themes.

## Architecture

### Project Structure

```text
- .circleci          # CircleCI pipeline configuration files
- .github            # GitHub configuration files
```

## Contribution

More details on how to contribute to this package can be found in the [CONTRIBUTING.md](docs/CONTRIBUTING.md) file.

### Minimal requirements

-   PHP 8.2

## Development setup

To build the package

PHP setup

-   `composer install`

## Installation

Composer install:

```bash
composer require --dev newsuk/nuk-wp-phpstan-config
```

## Usage

### Using the ruleset

Create a `phpstan.neon.dist` file in the root of your project and add the below config. Feel free to alter the `paths` based on your project requirements

```yml
parameters:
    level: max
    paths:
        # adjust the filename / directory name according to project needs.
        - plugin.php
        - includes/
```

### Usage with Composer

Add the following to `scripts` section in `composer.json` file and run `composer phpstan`

```json
"phpstan": "phpstan analyse --memory-limit=2048M"
```
Add the following to generate baseline file for existing plugins and run `composer phpstan-baseline`

```json
"phpstan-baseline": "phpstan analyse -b --allow-empty-baseline"
```

## Tagging and releasing

The content schema uses Semantic Versioning `semver` for versioning. The package is released using [GitHub Releases](https://docs.github.com/en/github/administering-a-repository/releasing-projects-on-github/about-releases). The release process is automated in Circle CI build step. To create a new release, follow these steps:

-   Update the relevant files with the new version. Commit the updated files.
-   Push the changes to the master branch, by merging the associated pull request
-   Create a release targeting the `main` branch within GitHub.
