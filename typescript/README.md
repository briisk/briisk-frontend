Briisk TypeScript Style Guide

## Interfaces

  <a name="interfaces--naming"></a><a name="1.1"></a>
  - [1.1](#interfaces--naming) Interfaces and types naming convention

    > Why? For consistancy. Be aware that using this style with classes can cause conflicts.

    ```javascript
    interface User {
      name: string;
    }
    type Product = {
      name: string;
    }
    ```
