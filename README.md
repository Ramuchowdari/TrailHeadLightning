# bFO Lightning Web Components starter kit

The idea behind starter kit is to kick start lightning development within bFO.

## Table of contents

- Installation Instructions

  - [Installing lwc-starter-kit using Salesforce DX](#installing-lwc-starter-kit-using-salesforce-dx)  

- [Optional installation instructions](#optional-installation-instructions)

- [Application Walkthrough](#application-walkthrough)

## Installation Instructions

- [Using Salesforce DX](#installing-lwc-starter-kit-using-salesforce-dx): This is the recommended installation option. Use this option if you are a developer who wants to experience the app and the code.

## Installing lwc-starter-kit using Salesforce DX

1. Set up your environment. Follow the steps in the [bfo-lwc tooling setup](https://schneider.atlassian.net/wiki/spaces/BFO/pages/1257932402/bFO+LWC+Tooling+Setup). The steps include
  
  - Install Salesforce CLI
  - Install Visual Studio Code
  - Installing nodejs
  - Installing [schneider developer pack extension](https://marketplace.visualstudio.com/items?itemName=siddharatha.schneider-salesforce-developer-extension-pack#overview)

2. Connect to your sandbox. For the sake of ease of documentation, i would assume that you would connect to an org with an alias name as bfospring19.

  ```
  sfdx force:auth:web:login -r https://test.salesforce.com -a bfospring19
  ```

3. Clone the repository:

  ```
  git clone https://github.com/siddharatha/lwc-starter-kit
  cd lwc-starter-kit
  ```

4. Map the working project to the sandbox you are working on

  ```
  sfdx force:config:set defaultusername=bfospring19
  ```

5. Push the app to your sandbox:

  ```
  sfdx force:source:push
  ```

6. Open the sandbox:

  ```
  sfdx force:org:open
  ```

## Optional Installation Instructions

This repository contains several files that are relevant if you want to integrate modern web development tooling to your Salesforce development processes, or to your continuous integration/continuous deployment processes.

### Code formatting

[Prettier](https://prettier.io/) is a code formatter used to ensure consistent formatting across your code base. To use Prettier with Visual Studio Code, install [this extension](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode) from the Visual Studio Code Marketplace. The [.prettierignore](/.prettierignore) and [.prettierrc](/.prettierrc) files are provided as part of this repository to control the behavior of the Prettier formatter.

### Code linting

[ESLint](https://eslint.org/) is a popular JavaScript linting tool used to identify stylistic errors and erroneous constructs. To use ESLint with Visual Studio Code, install [this extension](https://marketplace.visualstudio.com/items?itemName=salesforce.salesforcedx-vscode-lwc) from the Visual Studio Code Marketplace. The [.eslintignore](/.eslintignore) file is provided as part of this repository to exclude specific files from the linting process in the context of Lighning Web Components development.

### Pre-commit hook

This repository also comes with a [package.json](./package.json) file that makes it easy to set up a pre-commit hook that enforces code formatting and linting by running Prettier and ESLint every time you `git commit` changes.

To set up the formatting and linting pre-commit hook:

1. Install [Node.js](https://nodejs.org) if you haven't already done so
2. Run `npm install` in your project's root folder to install the ESLint and Prettier modules (Note: Mac users should verify that Xcode command line tools are installed before running this command.)

Prettier and ESLint will now run automatically every time you commit changes. The commit will fail if linting errors are detected. You can also run the formatting and linting from the command line using the following commands (check out [package.json](./package.json) for the full list):

```
npm run lint:lwc
npm run prettier
```

## Development workflow
