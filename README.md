# Syntax highlighter
[Package link for language-perl6 package][language-perl6]
## Instructions
Run `apm install language-perl6` in terminal or install `language-perl6` through the package manager
by pressing `Ctrl + ,` and then choosing the `Install` menu on the left side and searching.
## How do I use this?
This language grammar should automatically highlight `.p6`, `.pod6`, `.pm6` and
`.nqp` files. The language grammar will also detect files whose first
line includes `use v6`, a shebang whose last term before any whitespace is
`perl6` , `=begin pod`, or `my class`.

If you need to manually set it, `Perl 6 FE` in the bottom right corner of Atom:
![Bottom right corner of atom](/images/atom-language-perl6.png)

If you are having issues, the `language-perl` package is probably taking
precedence. To remedy this you can:

* Click the language name in the status-bar (`Ctrl+Shift+L`) and select `Perl 6 FE`
* If you want to permanently change the preferences for a file type,
  add the following to your `config.cson` (*Edit* → *Config*):

  ```coffee
  "*":
    core:
      customFileTypes: [
        'source.perl6fe': [
          'p6'
          'pm6'
          # Add pm and t if you want auto choose this highlighter for .pm or 't
          # files.
          'pm'
          't'
        ]
      ]
  ```

Please be aware that if you do not include the `t` extension
above, your `t` files will be highlighted with the `language-perl` highlighter unless the first line contains `use v6;`.

# Perl 6 code execution
## Installation
Requires the [language-perl6](#Syntax-highlighter) package.
## Integration
This package has integration with the Atom [script][script-package] package. With both this package and the `script` package you can execute
highlighted Perl 6 code or the whole document, even if it hasn't been saved using
a keyboard shortcut.

# nav-marker-plus
[Link to package on atom.io][nav-panel-plus]
You can get a right panel which will show all Routine's, Classes and Operators for Perl 6 code.
![nav-panel-plus](/images/nav-marker-plus.png)
## Instructions
Run `apm install nav-marker-plus` or install it from the package search in Atom by pressing `Ctrl + ,` then clicking `Install` and searching for `nav-marker-plus`
## How do I use this?
Put the [.nav-marker-rules](/config/.nav-marker-rules) in the root of a project you are working on. In your terminal go into that folder and open Atom with `atom .` or run `atom ~/path/to/your/project`. You can also go to the `File` menus and then choose `Open Folder...`
[script-package]: https://atom.io/packages/script
[language-perl6]: https://atom.io/packages/language-perl6
[nav-panel-plus]: https://atom.io/packages/nav-panel-plus
