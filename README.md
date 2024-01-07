<p align="center">
  <img src="images/logo.png" alt="VNF Scripting Language Logo">
</p>

<h1 align="center">VNF Scripting Language Extension for Visual Studio Code</h1>

Enhance your Visual Studio Code experience with syntax highlighting for VNF scripting language files. This extension provides an intuitive and efficient workflow for scripting in VNF, making it easier and more enjoyable.


## Table of Contents
- [Table of Contents](#table-of-contents)
- [Features](#features)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Download](#download)
  - [Installation](#installation)
  - [Running from Source](#running-from-source)
- [Known Issues](#known-issues)
- [License](#license)
- [FAQ / Troubleshooting](#faq--troubleshooting)
- [Credits](#credits)

## Features

- Syntax highlighting specifically designed for VNF scripting language.

## Getting Started

### Prerequisites

- [Visual Studio Code](https://code.visualstudio.com/download)

### Download

1. Visit the [Releases page](https://github.com/ev3rest/vnf-scripting-language/releases).
2. Select the latest version.
3. Download the `.vsix` file.

<details>
<summary>Visual Guide for Download</summary>

1. Navigate to the [Releases tab](https://github.com/ev3rest/vnf-scripting-language/releases) on the right side of the repository.
   
   ![Releases Tab](images/download/1.jpg "Releases Tab")

2. Select the latest release and download the `.vsix` file.

   ![Download .vsix file](images/download/2.jpg "Download .vsix File")

   *Hint: Version numbers follow the format where 1.2 is newer than 1.0, and 2.0 is newer than 1.2*

</details>

### Installation

1. Open Visual Studio Code.
2. Go to Extensions (`Ctrl+Shift+X` or `Cmd+Shift+X` on Mac).
3. Click on the "..." menu and select `Install from VSIX`.
   
   ![Install from VSIX](images/installation/2.jpg "Install from VSIX")

4. Navigate to the downloaded `.vsix` file and select 'Install'.
5. Reload Visual Studio Code if prompted.
6. Create a new file (`File` > `New File`).
7. Type `VNF` and select the relevant option. 

    *Note: Make sure to name the file with a `.vnf` extension. Example: `Chapter 1.vnf`.*

   ![Create VNF File](images/installation/7.jpg "Create VNF File")

8. Start creating your novel with VNF!

<details>
<summary>Running from Source</summary>

### Running from Source

1. Open a new VSCode window.
2. Go to `File` > `Open Folder` and select the `vnf-scripting-language` folder.
3. Press `F5` to run.
4. A new VSCode instance will open with the extension loaded.

*Note: Building from source requires the `vsce` npm package. To install it, run `npm install -g vsce`.*

</details>

## Known Issues

- Inconsistent highlighting in some instances of `[]`.

## License

This project is licensed under the MIT License - see the [LICENSE.txt](LICENSE.txt) for details.

## FAQ / Troubleshooting

*Q: Can I contribute to the development of this extension?*
**A: Absolutely! Contributions are welcome.**

## Credits

**Prototyping & Testing:**  
*wsan*

**Acknowledgments:**  
Special thanks to all the contributors who have helped make this extension a reality. Your efforts and dedication have been invaluable in developing and maintaining this project.

<p align="right">(<a href="#vnf-scripting-language-extension-for-visual-studio-code">back to top</a>)</p>
