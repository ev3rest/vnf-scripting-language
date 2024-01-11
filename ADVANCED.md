# Advanced Use and Customization

This document provides advanced guidelines and information for the VNF Scripting Language Extension for Visual Studio Code. It is intended for users who want to delve deeper into the extension's capabilities, customize it to their needs, and understand its underlying mechanisms.

## Table of Contents
- [Tokenization Engine](#tokenization-engine)
- [Custom Syntax Highlighting](#custom-syntax-highlighting)
- [Creating Custom Themes](#creating-custom-themes)
- [Contributing Customizations](#contributing-customizations)

## Tokenization Engine

The VNF Scripting Language Extension utilizes VS Code's powerful tokenization engine, which is powered by TextMate grammars. TextMate grammars are structured collections of regular expressions and can be written in plist (XML) or JSON format.

### Understanding TextMate Grammars

TextMate grammars are used to provide syntax highlighting in text editors like Visual Studio Code. They define how pieces of text should be highlighted based on their syntactic structure.

#### Overview of TextMate Grammars

1. **Scope-Based Matching**: TextMate grammars work by assigning scopes to pieces of text in a document. Each scope corresponds to a syntactic or semantic element of the language, like a keyword, variable, or comment.

2. **Regular Expressions**: These grammars use regular expressions to identify elements in the code. A matched text is assigned a specific scope.

3. **Grammar Files**: Defined in JSON or XML (plist) files, these include a series of patterns with regular expressions and corresponding scopes.

#### Key Components of a TextMate Grammar File

- **Patterns**: The core of the grammar. Patterns include regular expressions and the scope applied when the expression matches. They can be simple (for keywords) or complex (for nested structures).

- **Repository**: A collection of reusable named patterns, aiding in organizing complex grammars.

- **Includes**: Grammars can include other grammars, useful for languages embedding other languages.

- **Name and ScopeName**: The file starts with a name and a scopeName, the latter being a unique identifier for the grammar.

#### How Syntax Highlighting Works with TextMate Grammars

1. **Tokenization**: The editor tokenizes the text, breaking it into identifiable pieces (tokens) like keywords and strings.

2. **Applying Scopes**: Each token is assigned a scope based on the matching patterns.

3. **Styling**: The editor applies styles to these scopes using the current theme, determining the appearance of the highlighted text.

#### Customizing Syntax Highlighting

To customize syntax highlighting:

1. **Modify Existing Patterns**: Adjust regular expressions and scopes in existing patterns to change the highlighting. The language file with the corresponding grammars can be found in [vnf.tmLanguage.json](syntaxes/vnf.tmLanguage.json).

2. **Add New Patterns**: Define new patterns for additional syntactic elements specific to your language.

3. **Test Changes**: Regularly test your changes to ensure correct highlighting. You [complex.vnf](examples/complex.vnf) for testing purposes, as it covers a big portion of VNF's syntax.


## Custom Syntax Highlighting

Custom syntax highlighting can be adjusted or extended by modifying the TextMate grammar files.

### Editing Grammar Files
- Location of grammar files.
- Basic guidelines on editing these files.

### Testing Changes
- How to test changes to syntax highlighting.
- Tips for effective testing.

## Creating Custom Themes

You can create custom themes that complement or enhance the syntax highlighting provided by the extension.

### Theme Structure
- Basic structure of a VS Code theme.
- How to define colors and styles.

### Developing Your Theme
- Steps to develop a custom theme.
- Tips for theme design.

## Contributing Customizations

We encourage contributions to the extension, including new features, bug fixes, and enhancements.

### Contribution Guidelines
- Steps to contribute to the extension.
- Coding standards and best practices.

### Submitting Contributions
- Process for submitting contributions.
- Review and acceptance criteria.

---

For more detailed information about VS Code's extension capabilities and TextMate grammars, refer to the [official VS Code documentation](https://code.visualstudio.com/api/language-extensions/syntax-highlight-guide) and [TextMate grammars documentation](https://macromates.com/manual/en/language_grammars).

<p align="right">(<a href="#advanced-use-and-customization">back to top</a>)</p>
