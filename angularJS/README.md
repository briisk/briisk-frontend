Briisk AngularJS 1.x Style Guide

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
