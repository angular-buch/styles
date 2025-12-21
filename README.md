# `@angular-buch/styles`

This repository contains the global stylesheet to be used within the example application "BookManager" used in the German [Angular Book](https://angular.buch.com).

> :warning: This CSS Stylesheet is not used in the BookMonkey Versions (2-5) from the "Angular Buch".

## Installation

To install the package, run the following command:

```sh
npm i @angular-buch/styles
```

## Usage

After installing the package, you can import the SCSS stylesheet in your project:

```scss
@use '@angular-buch/styles';
```

Make sure to include the necessary build tools to compile SCSS into CSS.

## Publishing

This package is automatically published to NPM when a new version tag is pushed to GitHub.

### Release Process

1. Update the version in `package.json`:
   ```sh
   npm version patch  # or minor/major
   ```

2. Push the tag to GitHub:
   ```sh
   git push origin --tags
   ```

3. The GitHub Action will automatically:
   - Build the package
   - Publish to NPM under `@angular-buch/styles`

### Prerequisites

- NPM_TOKEN secret must be configured in GitHub repository settings
- Token must have publish permissions for the `@angular-buch` organization
