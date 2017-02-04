# Using Atom as a Perl 6 IDE
So you've started to write some code in Perl 6. You may now be asking yourself, "How can I make this programming experience _more awesome_?"

To that question, please see these three enhancements to the Atom text editor:

* [Syntax highlighter](#syntax-highlighter)
* [Perl 6 code execution](#perl-6-code-execution)
* [Indexing of classes, routines and operators](#indexing-of-classes-routines-and-operators)

# Syntax highlighter
[Package link for language-perl6 package][language-perl6]

### What does this do?
This will properly highlight various elements of your perl6 code.

### Installation
Run `apm install language-perl6` in terminal or install `language-perl6` through the package manager
by pressing `Ctrl + ,` and then choosing the `Install` menu on the left side and searching. Note that you should install the plugin that is maintained by the user `perl6`.

### How do I use this?
This language grammar should automatically highlight `.p6`, `.pod6`, `.pm6` and
`.nqp` files. The language grammar will also detect files whose first
line includes `use v6`, a shebang whose last term before any whitespace is
`perl6` , `=begin pod`, or `my class`.

If you need to manually set it, click on the on the bottom right corner of Atom and select `Perl 6 FE`:

![Bottom right corner of atom](/images/atom-language-perl6.png)

### Note

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
          # Add pm and t if you want to auto choose this highlighter for .pm or .t
          # files.
          'pm'
          't'
        ]
      ]
  ```

Please be aware that if you do not include the `t` extension
above, your `t` files will be highlighted with the `language-perl` highlighter unless the first line contains `use v6;`.

If you do not ever expect to write Perl 5 code, then you may as well make these changes.

# Perl 6 code execution
[Link to script package on atom.io][script-package]

### What does this do?
This will allow you to execute portions of your code that you highlight with your cursor as if it was run on the command line.

### Installation
Run `apm install script` and install the [syntax highlighter language-perl6](#syntax-highlighter) if you have not already done so.

### How do I use this?
Make sure you have set the grammar type to `Perl 6 FE`
![Bottom right corner of atom](/images/atom-language-perl6.png)
Then you can press `Ctrl + Shift + B` on Linux. For other operating systems see
the packages [readme page][script-package].

If no text is selected it will run the file direction if the file has been saved
and you have made no modifications. If you have made changes since it was last saved,
it will run using the current text in the screen buffer. If you have text selected
it will evaluate only the selection. 

# Indexing of classes, routines and operators
[Link to package on atom.io for nav-marker-plus package][nav-panel-plus]
You can get a right panel which will show all Routines, Classes and Operators for Perl 6 code.
![nav-panel-plus](/images/nav-marker-plus.png)

### What does this do?
This will display a sidebar on the right side of the editor that lists all of the subroutines, classes, and operators in the current file. Clicking on any of these things will take you to where they are defined.

### Installation
Run `apm install nav-marker-plus` or install it from the package search in Atom by pressing `Ctrl + ,` then clicking `Install` and searching for `nav-marker-plus`

### How do I use this?
Put the [.nav-marker-rules](/config/.nav-marker-rules) in the root of a project you are working on. In your terminal go into that folder and open Atom with `atom .` or run `atom ~/path/to/your/project`. You can also go to the `File` menus and then choose `Open Folder...`

### Note

Eventually we will have instructions on how to make it specific to
perl6 filetypes and make it apply globally, but for now you can use .nav-marker-rules
as the instructions show. Any files opened in that project's window will also take on
the config, even if they're in another folder, as long as they're still part of the
same `Project` context in Atom.

[script-package]: https://atom.io/packages/script
[language-perl6]: https://atom.io/packages/language-perl6
[nav-panel-plus]: https://atom.io/packages/nav-panel-plus
