Briisk AngularJS 1.x Style Guide

## Scripts in package.json

**npm run init** - to initialize application, should be run once after git clone

**npm start** - to start application, should run application in the development mode

**npm start:production** - to start application, should run application in the production mode

**npm run build:production** - to build application, should build application in the production mode

**npm run build:staging** - to build application, should build application in the staging mode

**npm run build:workspace** - to build application, should build application in the workspace mode

**npm run build:dev** - to build application, should build application in the development mode

**npm test** - to test application, should run test with watch flag and in the continuous mode

**npm run test:ci** - to test application, should run test without watch flag and in the single run mode

**npm run lint** - to lint application, should run all linters once

## Project configuration files
Environment configuration files should be placed into: `src/environmenjs/` directory (following Angular CLI pattern).

Environment configuration directory should contains 4 files:

```
├── environment.js - localhost config
├── environment.dev.js - development server config
├── environment.stag.js - stagging server config
├── environment.prod.js - production server config
```

Which will be used for providing suitable data for every environment.

Example of configuration file:
```
export const environment = {
  production: false,
  apiUrl: 'http://example.com/api/',
};
```

#### Repository
Configuration files used for build process should not be stored in remote repository (should be added to `.gitignore` 
file) owing to the possibility of including sensitive data. 

All configuration files  should be replaced with matching `*.js.example` file. 

Files stored in remote reposition:

```
├── environment.js.example
├── environment.dev.js.example
├── environment.stag.js.example
├── environment.prod.js.example
```

Example of `environment.dev.js.example`:
```
export const environment = {
  production: false,
  apiUrl: 'http://example.com/api/',
  gcmKey: 'ADD_GCM_KEY_HERE'
};
```

Generating files under `src/environmenjs/` should be done automatically using:

```
  npm run init
```
bash command triggered after `npm run init` should be implemented additionally by developer
