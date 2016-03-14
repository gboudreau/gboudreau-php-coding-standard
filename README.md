# gboudreau-php-coding-standard
Guillaume Boudreau's PHP Coding Standard for PHP_CodeSniffer

This is essentially the PEAR coding standard, with some exceptions:

- no line length limit (normally 85 characters max)
- allows the 'continue' statement inline: `if (...) continue;`
- TRUE, FALSE and NULL must be uppercase (normally lowercase)
- function declaration starting brace must be on same line (normally needs to be on the next line)

I also added some other standards that I like, such as:

- Generic.Functions.FunctionCallArgumentSpacing
- PSR2.Classes.PropertyDeclaration.Underscore
- PSR2.ControlStructures.ElseIfDeclaration
- PSR2.ControlStructures.SwitchDeclaration
- PSR2.Files.EndFileNewline.NoneFound
- PSR2.Methods.FunctionCallSignature
- Squiz.Classes.ValidClassName
- Squiz.ControlStructures.ForEachLoopDeclaration
- Squiz.Functions.FunctionDeclarationArgumentSpacing
- Squiz.PHP.LowercasePHPFunctions
- Squiz.WhiteSpace.[LanguageConstructSpacing|SemicolonSpacing|SuperfluousWhitespace]

## Requirements

PHP_CodeSniffer:
```bash
composer require squizlabs/php_codesniffer
```

## Usage

1\. Run `phpcs` by specifying the path to the `GBoudreauCodingStandard` folder:
```bash
vendor/bin/phpcs -ps --standard=path/to/GBoudreauCodingStandard/ .
```

2\. Optionally, always run it in a Git `pre-commit` hook:
```bash
#!/usr/bin/env bash

if [ ! -f vendor/bin/phpcs ]; then
    echo "Error: missing PHP_CodeSniffer; vendor/bin/phpcs not found"
    exit 1
fi

echo
echo "Checking coding standards using PHP_CodeSniffer..."
vendor/bin/phpcs -ps --no-colors --standard=_material/NetliftCodingStandard/ .
```
