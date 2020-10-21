# PHP best practices
First of all, if you still think that PHP is an obsolete, nonperforming, and even dangerous language, please take a loot at https://stitcher.io/blog/php-in-2019

# Golden rule of every programming language

**Validate input, escape output**

# Versions

If creating a new project, always use the latest php version (7.4 to date).  PHP 7.x is so many times faster than 5.x, and includes language features that are useful.

If you want to use latest PHP version on a Mac, even though it comes with PHP preinstalled, it is an old version.  you can use a docker image for that purpose (https://phpdocker.io/generator), or install a newer version directly on your mac with Homebrew

`brew install php@7.4`

Version history of language features you should be aware of

- 7.0 - https://feryn.eu/blog/php-7-is-now-available-new-features-improvements/
- 7.1 - https://www.cloudways.com/blog/whats-new-in-php-7-1/
- 7.2 - https://www.zimuel.it/blog/the-new-features-php72
- 7.3 - https://stitcher.io/blog/new-in-php-73
- 7.4 - https://stitcher.io/blog/new-in-php-74
# IDE

You can code php with any text editor, however if you plan to get serious, the de-facto IDE would be PHPStorm (https://www.jetbrains.com/phpstorm/)

# Coding Style

PHP has many “PHP Standard Recommendation” (PSR for short) that are intended to promote interoperability among different packages and frameworks developed by the PHP community.  The relevant PSR’s around coding style are PSR-1 (https://www.php-fig.org/psr/psr-1/) and PSR-12 (https://www.php-fig.org/psr/psr-12/).

There are several tools that will help you check your code against those standards like PHP Code Sniffer (https://github.com/squizlabs/PHP_CodeSniffer), PHP Coding Standard Fixer (https://cs.symfony.com/), etc.  Several IDE’s like PHPStorm have some of those integrated, with real time hinting.

PHP Code Sniffer:

    phpcs --standard=PSR1 /path/to/code-directory

PHP Code Beautifier and Fixer:

    phpcbf -w --standard=PSR1 file.php

PHP Coding Standard Fixer:

    php-cs-fixer fix -v --rules=@PSR1 file.php

Aside from a standard code, it is always good to write actual clean code as described at https://github.com/jupeter/clean-code-php

As with any programming language, please avoid code smells (https://refactoring.guru/refactoring/smells)

# Namespaces and autoloading

To encourage separation of concerns, as well as modularization, PHP has namespacing capabilities (https://www.php.net/language.namespaces).
There are relevant PSR’s about namespaces and autoloading (everybody hates having to do `require_once…` of every dependency).  Please get familiar with PSR-4 (https://www.php-fig.org/psr/psr-4/).  Package management tools like Composer (https://getcomposer.org/) will nicely handle autoloading, including your custom namespaces via PSR-4 (https://getcomposer.org/doc/04-schema.md#psr-4).

# Dependency Management

while you are at PHP Composer site, please get familiar with this tool:


- Getting started: https://getcomposer.org/doc/00-intro.md
- Installation: https://getcomposer.org/download/

it is the most popular dependency management tool, containing thousands of packages indexed at https://packagist.org/

On most of our PHP projects we use composer already, if it is the first time setting up the project, most likely you’ll need to download the project dependencies with a “composer install” command.

# Standard PHP Library (SPL)

PHP already has built in a wide range of utility objects that often developers are unfamiliar with and end up writing them from scratch.  please refer to https://www.php.net/book.spl to get familiar with SPL.

# Design Patterns

Please get familiar with Design Patterns, you can find PHP specific examples at https://designpatternsphp.readthedocs.io/en/latest/README.html 

# SOLID Principles
- Single responsibility
    - A class should only have one job
- Open-closed
    - open for extension, closed for modification
- Liskov substitution
    - every subclass or derived class should be substitutable for their base/parent class without breaking the application
- Interface Segregation
    - A class should never be forced to implement an interface it does not use, or depend on methods they do not use
- Dependency Inversion
    - Entities must depend on abstractions and not on concretions.  High level modules must not depend on low level modules.


https://scotch.io/bar-talk/s-o-l-i-d-the-first-five-principles-of-object-oriented-design


The above will achieve Low coupling, High cohesion, which makes any code base to be easy to maintain (https://medium.com/clarityhub/low-coupling-high-cohesion-3610e35ac4a6).

# Security

Security is especially  critical in PHP.  Please take a look at https://paragonie.com/blog/2015/08/gentle-introduction-application-security for a general introduction to application security.

You can also take a look at https://paragonie.com/blog/2017/12/2018-guide-building-secure-php-software for useful guidelines on this topic specific for PHP. Yes, that guide can be long… to the very least get familiar with

- Data filtering - https://www.php.net/book.filter
    - Sanitization - https://www.php.net/filter.filters.sanitize
    - Validation - https://www.php.net/filter.filters.validate
# Unit Testing

The de-facto PHP unit testing tool is PHPUnit (https://phpunit.de/)


## Test anatomy (AAA)
1. Arrange - create stubs, spies, fixtures…
2. Act - execute the method to be tested
3. Assert - output, spies, etc…


## Best Practices
- Black box testing, test only public methods
- Stay within the test, minimize external helpers and abstractions as much as possible
- Avoid global fixtures, add data per test


# Documenting your code

Please get familiar with PHPDoc (https://docs.phpdoc.org/latest/references/phpdoc/index.html).  Several IDE’s like PHPStorm will automatically generate PHPDoc blocks and hugely benefit from its context, especially since PHP is not a strongly typed language (yet, recent PHP versions you can use type hinting), and will warn you about unexpected data types and arguments based on the PHPDoc blocks.


# Other resources

You can take a look at other resources like

- https://phpbestpractices.org/
- https://phptherightway.com/
- https://phpthewrongway.com/
- https://blog.codinghorror.com/code-smells/
- https://www.php-fig.org/psr/

