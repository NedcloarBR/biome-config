<div align="center"> 

![BiomeJS Logo](https://raw.githubusercontent.com/biomejs/resources/main/svg/slogan-light-transparent.svg)

# @nedcloarbr/biome-config

**[BiomeJS](https://biomejs.dev/) Configuration used by [NedcloarBR](https://github.com/NedcloarBR) in their projects**

[![GitHub](https://img.shields.io/github/license/NedcloarBR/biome-config)](https://github.com/NedcloarBR/biome-config/blob/master/LICENSE)
[![npm](https://img.shields.io/npm/v/@nedcloarbr/biome-config?color=crimson&logo=npm&style=flat-square)](https://www.npmjs.com/package/@nedcloarbr/biome-config)

</div>

**Table of Contents**

- [Description](#description)
- [Installation](#installation)
- [Usage](#usage)
- [To-Do](#to-do)

## Description

Configuring a linter and formatter, such as `BiomeJS`, is crucial for maintaining consistent, readable, and error-free code. Linters ensure uniform coding standards and early error detection, saving debugging time. Formatters automate code structuring, enhancing readability and maintenance. These tools increase productivity by allowing developers to focus on critical tasks. They also enforce quality standards, creating a professional development environment. In CI/CD workflows, they ensure code adherence to quality standards, preserving codebase integrity.

The package includes configuration for [`NestJS`](https://nestjs.com/)

## Installation

You can use the following command to install this package.

```sh
npm install --save-dev --save-exact @biomejs/biome @nedcloarbr/biome-config
yarn add --dev --exact @biomejs/biome @nedcloarbr/biome-config
pnpm install --save-dev --save-exact @biomejs/biome @nedcloarbr/biome-config
bun add --dev --exact @biomejs/biome @nedcloarbr/biome-config
```

> [!WARNING]
> At the moment BiomeJS doesn't support Yarn PnP completely \
> Discussion for add this support: https://github.com/biomejs/biome/discussions/3393 \
> If you're using Yarn Classic (v1.x) you don't have to worry about this \
> To opt out of using PnP in Yarn Modern (^v2.x), do the following

```yml
# .yarnrc.yml
nodeLinker: node-modules
```

## Usage

### [`NestJS`](https://nestjs.com/)

```jsonc
// biome.json
{
  "extends": ["@nedcloarbr/biome-config/nestjs"]
  // ...
}
```

## To-Do

Add support for other types of projects

- [ ] ReactJS
  - [ ] Vanilla
  - [ ] Vite
  - [ ] NextJS
- [ ] NodeJS
  - [ ] Vanilla
  - [ ] TypeScript
