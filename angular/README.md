Briisk Angular >= 2.x Style Guide


## Project configuration files
Environment configuration files should be placed into: `src/environments/` directory (following Angular CLI pattern).

Environment configuration directory should contains 4 files:

```
├── environment.ts - localhost config
├── environment.dev.ts - development server config
├── environment.stag.ts - stagging server config
├── environment.prod.ts - production server config
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

All configuration files  should be replaced with matching `*.ts.example` file. 

Files stored in remote reposition:

```
├── environment.ts.example
├── environment.dev.ts.example
├── environment.stag.ts.example
├── environment.prod.ts.example
```

Example of `environment.dev.ts.example`:
```
export const environment = {
  production: false,
  apiUrl: 'http://example.com/api/',
  gcmKey: 'ADD_GCM_KEY_HERE'
};
```

Generating files under `src/environments/` should be done automatically using:

```
  npm run init
```
bash command triggered after `npm run init` should be implemented additionally by developer
