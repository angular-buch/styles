# `@angular-buch/styles`

This repository contains the global stylesheet to be used within the example application "BookManager" from the German [Angular Book](https://angular.buch.com) (1st edition, 2026)

> :warning: This CSS Stylesheet is **not** used in the older **BookMonkey** versions 2-5.

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

This package is published to NPM via GitHub Actions when a new version tag is pushed to GitHub.
The workflow uses [trusted publishing](https://docs.npmjs.com/trusted-publishers/) (OIDC), so no NPM token is needed.
Releases are [staged](https://docs.npmjs.com/staged-publishing): CI uploads the new version, but it only becomes public after a maintainer approves it with 2FA.

### Release Process

1. Update the version in `package.json` (creates a commit and a `v*` tag):
   ```sh
   npm version patch  # or minor/major
   ```

2. Push the commit and the tag to GitHub:
   ```sh
   git push --follow-tags
   ```

3. The GitHub Action will automatically:
   - Build the package
   - Stage the new version on NPM under `@angular-buch/styles`

4. Approve the staged version (requires `npm login` and 2FA). The stage ID is printed in the workflow log:
   ```sh
   npm stage list @angular-buch/styles   # show staged versions and their IDs
   npm stage approve <stage-id>
   ```

   Use `npm stage view <stage-id>` or `npm stage download <stage-id>` to inspect a staged version before approving it,
   and `npm stage reject <stage-id>` to discard it.
   Alternatively, staged versions can be approved in the **Staged Packages** tab on npmjs.com.

### Prerequisites

- A trusted publisher must be configured in the NPM package settings:
  GitHub Actions, organization `angular-buch`, repository `styles`, workflow `publish.yml`, no environment
- "Allow npm publish" stays unchecked, so that every release requires staged publishing
- Approving requires an NPM account with publish rights for `@angular-buch/styles` and 2FA enabled
