# Advanced Use and Customization

This document provides detailed guidance and insights for the VNF Scripting Language Extension for Visual Studio Code. It is designed for users who wish to explore the extension's advanced capabilities, customize it according to their needs, and understand its technical details.

## Table of Contents
- [Advanced Use and Customization](#advanced-use-and-customization)
  - [Table of Contents](#table-of-contents)
  - [Understanding TextMate Grammars](#understanding-textmate-grammars)
    - [Overview of TextMate Grammars](#overview-of-textmate-grammars)
    - [Key Components of a TextMate Grammar File](#key-components-of-a-textmate-grammar-file)
    - [How Syntax Highlighting Works with TextMate Grammars](#how-syntax-highlighting-works-with-textmate-grammars)
    - [Customizing Syntax Highlighting](#customizing-syntax-highlighting)
  - [Creating Custom Themes](#creating-custom-themes)
  - [Contributing Customizations](#contributing-customizations)

## Understanding TextMate Grammars

TextMate grammars are crucial for providing syntax highlighting in text editors such as Visual Studio Code. They define the rules for how text is highlighted based on its syntactic structure.

### Overview of TextMate Grammars

1. **Scope-Based Matching**: TextMate grammars assign scopes to text segments in a document, corresponding to syntactic or semantic elements like keywords, variables, or comments.

2. **Regular Expressions**: These grammars utilize regular expressions to detect code elements, assigning a specific scope to matched text.

3. **Grammar Files**: These are JSON or XML (plist) files containing patterns of regular expressions and their associated scopes.

### Key Components of a TextMate Grammar File

- **Patterns**: Essential elements of the grammar, consisting of regular expressions and their corresponding scopes. These can range from simple keyword patterns to complex nested structures.

- **Repository**: A set of reusable named patterns, helping to organize and streamline complex grammars.

- **Includes**: Allows grammars to include other grammars, beneficial for languages that incorporate multiple languages.

- **Name and ScopeName**: The file begins with these elements, with ScopeName serving as the grammar's unique identifier.

### How Syntax Highlighting Works with TextMate Grammars

1. **Tokenization**: The editor breaks down text into tokens (like keywords and strings) using the grammar's patterns.

2. **Applying Scopes**: Each token is assigned a scope based on its pattern match.

3. **Styling**: The editor styles these scopes according to the active theme, defining the visual presentation of the highlighted text.

### Customizing Syntax Highlighting

To tailor syntax highlighting for your needs:

1. **Modify Existing Patterns**: Update the regular expressions and scopes in the [vnf.tmLanguage.json](syntaxes/vnf.tmLanguage.json) file to alter the existing highlighting behavior.

    Current structure is as such:
    - [Comments](https://github.com/ev3rest/vnf-scripting-language/blob/759d295568083007eda197f88d8fbd66d1231f59/syntaxes/vnf.tmLanguage.json#L7). Denoted by a `#` sign.
    - [Strings](https://github.com/ev3rest/vnf-scripting-language/blob/759d295568083007eda197f88d8fbd66d1231f59/syntaxes/vnf.tmLanguage.json#L12). Bound by double quotes `" "`.
      - [Escape Character](https://github.com/ev3rest/vnf-scripting-language/blob/759d295568083007eda197f88d8fbd66d1231f59/syntaxes/vnf.tmLanguage.json#L18). By default, denoted by `\`
      - [Angled brackets nested variables](https://github.com/ev3rest/vnf-scripting-language/blob/759d295568083007eda197f88d8fbd66d1231f59/syntaxes/vnf.tmLanguage.json#L23). Bound by `< >`.
      - [Square brackets nested variables](https://github.com/ev3rest/vnf-scripting-language/blob/759d295568083007eda197f88d8fbd66d1231f59/syntaxes/vnf.tmLanguage.json#L33). Bound by `[ ]`.
      - [Curly brackets nested variables](https://github.com/ev3rest/vnf-scripting-language/blob/759d295568083007eda197f88d8fbd66d1231f59/syntaxes/vnf.tmLanguage.json#L43). Bound by `{ }`.
    - [Built-in keywords](https://github.com/ev3rest/vnf-scripting-language/blob/759d295568083007eda197f88d8fbd66d1231f59/syntaxes/vnf.tmLanguage.json#L55). Examples: `enter`, `contains`, `jump`, `at`, etc.
    - [Capitalized words](https://github.com/ev3rest/vnf-scripting-language/blob/759d295568083007eda197f88d8fbd66d1231f59/syntaxes/vnf.tmLanguage.json#L60). Examples: `JUMP POINT` and `SECTOR`.
    - [Standalone variables](https://github.com/ev3rest/vnf-scripting-language/blob/759d295568083007eda197f88d8fbd66d1231f59/syntaxes/vnf.tmLanguage.json#L65). Variables, bound by `[ ]`, `<>` and `{ }`.
    - [Functions](https://github.com/ev3rest/vnf-scripting-language/blob/759d295568083007eda197f88d8fbd66d1231f59/syntaxes/vnf.tmLanguage.json#L82). Function calls in `function(argument: Optional)` format.
    - [Conditional Stetements](https://github.com/ev3rest/vnf-scripting-language/blob/759d295568083007eda197f88d8fbd66d1231f59/syntaxes/vnf.tmLanguage.json#L87). Examples: `if`, `else`, `endif`.
      

2. **Add New Patterns**: Introduce new patterns for unique syntactic elements of the VNF scripting language. 

3. **Test Changes**: Consistently test your modifications for accuracy, using files like [complex.vnf](examples/complex.vnf) that cover a broad spectrum of the VNF syntax.

## Creating Custom Themes

Developing custom themes to complement the syntax highlighting is possible, though not covered here in detail. The [official documentation](https://code.visualstudio.com/api/extension-guides/color-theme#syntax-colors) provides comprehensive guidance on this topic.

## Contributing Customizations

Contributions of new features, bug fixes, and enhancements to the extension are highly encouraged and appreciated.

---

For additional information about VS Code's extension features and TextMate grammars, consult the [official VS Code documentation](https://code.visualstudio.com/api/language-extensions/syntax-highlight-guide) and the [TextMate grammars manual](https://macromates.com/manual/en/language_grammars).

<p align="right">(<a href="#advanced-use-and-customization">back to top</a>)</p>
