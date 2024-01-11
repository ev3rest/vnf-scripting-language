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
  - [Modifying the Icon](#modifying-the-icon)
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

1. **Modify Existing Patterns**: Enhance or adjust the syntax highlighting by editing the regular expressions and scopes in the [vnf.tmLanguage.json](syntaxes/vnf.tmLanguage.json) file. This file contains the rules defining how different language constructs in VNF are highlighted. The current structure includes:

    - **Comments**: Marked by a `#` sign. [View Definition](https://github.com/ev3rest/vnf-scripting-language/blob/759d295568083007eda197f88d8fbd66d1231f59/syntaxes/vnf.tmLanguage.json#L7)
    - **Strings**: Enclosed within double quotes `" "`. [View Definition](https://github.com/ev3rest/vnf-scripting-language/blob/759d295568083007eda197f88d8fbd66d1231f59/syntaxes/vnf.tmLanguage.json#L12)
      - **Escape Characters**: Typically denoted by `\`. [View Definition](https://github.com/ev3rest/vnf-scripting-language/blob/759d295568083007eda197f88d8fbd66d1231f59/syntaxes/vnf.tmLanguage.json#L18)
      - **Angled Brackets Nested Variables**: Bound by `< >`. [View Definition](https://github.com/ev3rest/vnf-scripting-language/blob/759d295568083007eda197f88d8fbd66d1231f59/syntaxes/vnf.tmLanguage.json#L23)
      - **Square Brackets Nested Variables**: Bound by `[ ]`. [View Definition](https://github.com/ev3rest/vnf-scripting-language/blob/759d295568083007eda197f88d8fbd66d1231f59/syntaxes/vnf.tmLanguage.json#L33)
      - **Curly Brackets Nested Variables**: Bound by `{ }`. [View Definition](https://github.com/ev3rest/vnf-scripting-language/blob/759d295568083007eda197f88d8fbd66d1231f59/syntaxes/vnf.tmLanguage.json#L43)
    - **Built-in Keywords**: Such as `enter`, `contains`, `jump`, `at`, etc. [View Definition](https://github.com/ev3rest/vnf-scripting-language/blob/759d295568083007eda197f88d8fbd66d1231f59/syntaxes/vnf.tmLanguage.json#L55)
    - **Capitalized Words**: Examples include `JUMP POINT` and `SECTOR`. [View Definition](https://github.com/ev3rest/vnf-scripting-language/blob/759d295568083007eda197f88d8fbd66d1231f59/syntaxes/vnf.tmLanguage.json#L60)
    - **Standalone Variables**: Variables encased in `[ ]`, `<>` and `{ }`. [View Definition](https://github.com/ev3rest/vnf-scripting-language/blob/759d295568083007eda197f88d8fbd66d1231f59/syntaxes/vnf.tmLanguage.json#L65)
    - **Functions**: Formatted as `function(argument: Optional)`. [View Definition](https://github.com/ev3rest/vnf-scripting-language/blob/759d295568083007eda197f88d8fbd66d1231f59/syntaxes/vnf.tmLanguage.json#L82)
    - **Conditional Statements**: Including `if`, `else`, `endif`. [View Definition](https://github.com/ev3rest/vnf-scripting-language/blob/759d295568083007eda197f88d8fbd66d1231f59/syntaxes/vnf.tmLanguage.json#L87)
    
    Feel free to adjust or expand these patterns to better align with your needs.

2. **Add New Patterns**: Introduce new patterns for unique syntactic elements of the VNF scripting language.

    All new patterns must be added in the following format:
    ```
    {
    "comment": "Optional. Describe what this pattern does.",
    "name": "scope.name",
    "matches": "put your regex here"
    }
    ```

3. **Test Changes**: Consistently test your modifications for accuracy, using files like [complex.vnf](examples/complex.vnf) that cover a broad spectrum of the VNF syntax.

## Creating Custom Themes

Developing custom themes to complement the syntax highlighting is possible, though not covered here in detail. The [official documentation](https://code.visualstudio.com/api/extension-guides/color-theme#syntax-colors) provides comprehensive guidance on this topic.

## Modifying the Icon

If you'd like to modify the extension icon, we have provided the `.psd` and `.clip` files [here](images/logo/). Modifying the [VNF_logo.png](images/logo/VNF_Logo.png) file will change the logo of the extension.

## Contributing Customizations

Contributions of new features, bug fixes, and enhancements to the extension are highly encouraged and appreciated.

---

For additional information about VS Code's extension features and TextMate grammars, consult the [official VS Code documentation](https://code.visualstudio.com/api/language-extensions/syntax-highlight-guide) and the [TextMate grammars manual](https://macromates.com/manual/en/language_grammars).

<p align="right">(<a href="#advanced-use-and-customization">back to top</a>)</p>
