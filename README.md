<div align='center'>
  <h1> SemVer & NVM & NPM & Yarn </h1>
</div>

<!-- ################################################################ -->

# Table of Contents

- [Semantic Versioning (semver)](#semantic-versioning-semver)
- [Node Version Manager (NVM)](#node-version-manager-nvm)
- [Node Package Manager (NPM)](#node-package-manager-npm)
  - [Bump/Updating NPM](#bumpupdating-nodejs)
  - [Bump/Updating Node.js](#bumpupdating-nodejs)
  - [Installing NPM packages](#installing-npm-packages)
  - [Uninstalling a package](#uninstalling-a-package)
  - [Listing installed dependencies](#listing-installed-dependencies)
  - [Viewing package info](#viewing-package-info)
  - [Checking for releases](#checking-for-releases)
  - [Bump/Updating NPM packages](#bumpupdating-npm-packages)
  - [Environment Variables](#environment-variables)
  - [Creating a package.json file](#creating-a-packagejson-file)
  - [Creating a .gitignore file](#creating-a-gitignore-file)
- [Yarn Package Manager ](#yarn-package-manager)

<!-- ################################################################ -->

# Semantic Versioning (semver)

Major.Minor.Patch

- Major: breaking releases. API might break.
- Minor: new features. API does not break.
- Patch: bug fixes.

```bash
"package": "^1.0.0", // 1.x
"package": "~1.0.0", // 1.0.x
"package": "1.0.0",  // Exact version.
```
The caret (^) character tells the package manager to install any version starting with the Major version.

The tilde (~) character tells the package manager to install any version starting with the Major.Minor version.

---

<!-- ################################################################ -->

# Node Version Manager (NVM)

## Installing [Node.js](https://nodejs.org/en) with NVM

First, install [Node Version Manager](https://github.com/nvm-sh/nvm) (NVM):
```bash
wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
```
Check installation:
```bash
command -v nvm 
```
Install a specific version of Node.js:
```
nvm install <version>
```
Or install Node.js LTS version:
```bash
nvm install --lts
```
Alternatively, install Node.js latest version:
```bash
nvm install node
```
List Node.js installed versions:
```bash
nvm list
```
Use a specific installed version of Node.js:
```bash
nvm use <version>
```
Or use the LTS version:
```bash
nvm use --lts
```
Or use the latest version:
```bash
nvm use node
```

---

<!-- ################################################################ -->

# Node Package Manager (NPM) 

## Bump/Updating NPM 

NPM is shipped standard with Node.js:
```bash
node -v && npm -v
```
- Update NPM to the latest version:

```bash
npm i -g npm@latest
```
- Flags: `i` stands for install, and `-g` for global.

<!-- ################################################################ -->

## Bump/Updating Node.js

- Update Node.js to a specific version (for example, to version 20.11.1):

```bash
npm i -g node@20.11.1 --force
```

- Updating Node.js to the latest version:

```bash
npm i -g node@lts
```

<!-- ################################################################ -->

## Installing NPM packages

- Install all package dependencies from the `package.json` file:

```bash
npm i
```

### Install a package as a development dependency

```bash
npm i <dev-dependency> --save-dev
```

### Install a package as a production dependency

```bash
npm i <production-dependency> --save
```

<!-- ################################################################ -->

## Uninstalling a package

```bash
npm un <package_name>
```

<!-- ################################################################ -->

## Listing installed dependencies

```bash
npm list --depth=0
```

<!-- ################################################################ -->

## Viewing package info

```bash
npm view <package_name> dependencies
```

<!-- ################################################################ -->

## Checking for releases

```bash
npm outdated
```

<!-- ################################################################ -->

## Bump/Updating NPM packages

- Updating only minor and patch releases:

```bash
npm update  
```

- Updating a package to a specific version:

```bash
npm install <package_name>@<specific_version>
```

- Updating all NPM packages to the latest version. First, install the update manager:

```bash
npm i -g npm-check-updates
```
```bash
ncu -u && npm i
```

<!-- ################################################################ -->

## Environment Variables 

The following commands are intended for execution in a Terminal interface of a Linux-like system.

To set an env. variable to development mode:

```bash
export NODE_ENV=development
```

To set an env. variable to production mode:

```bash
export NODE_ENV=production
```

To simulate a dynamic port assigned by the host:

```bash
export PORT=5000
```

To unset:

```bash
unset NODE_ENV PORT
```

<!-- ################################################################ -->

## Creating a `package.json` file

```bash
npm init --yes
```

<!-- ################################################################ -->

## Creating a `.gitignore` file

```bash
npm install -g gitignore && gitignore node
```

---

<!-- ################################################################ -->

# Yarn Package Manager 

## Installing Yarn

- [Enabling Corepack, a tool shipped by default with Node.js](https://yarnpkg.com/getting-started/install):
```bash
corepack enable && yarn init -2
```

## Bump/Updating Yarn

- [Updating Yarn](https://yarnpkg.com/getting-started/install#updating-yarn):
```bash
yarn set version stable && yarn install && yarn -v
```

## Installing Yarn packages

- Install all package dependencies from the `package.json` file:
```bash
yarn install
```

### Install a package as a development dependency
```bash
yarn add <dev-dependency> [--dev/-D]
```

### Install a package as a production dependency
```bash
yarn add <production-dependency>
```

## Uninstalling a package
```bash
yarn remove <package_name>
```

## Listing installed dependencies
```bash
npm ls --depth 0
```

## Viewing package info
```bash
yarn info <package_name>
```

## Bump/Updating Yarn packages

- Updating a package to a specific version:
```bash
yarn add <package_name>@<specific_version>
```

- Updating outdated Yarn packages version:
```bash
yarn upgrade-interactive [--latest]
```

## Environment Variables

The Yarn commands for setting, unsetting, and simulating environment variables are the same as for npm.

## Creating a `package.json` file

```bash
yarn init --yes
```

## Creating a `.gitignore` file

```bash
yarn add gitignore-parser && gitignore node
```

---

# References

[1] https://github.com/nvm-sh/nvm

[2] https://docs.npmjs.com/cli/v10/commands

[3] https://www.npmjs.com/package/npm-check-updates

[4] https://nodejs.org/en/learn/getting-started/nodejs-the-difference-between-development-and-production

[5] https://en.wikipedia.org/wiki/Environment_variable
