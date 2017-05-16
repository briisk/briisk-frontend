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

## Types

  <a name="type--any"></a><a name="2.1"></a>
  - [2.1](#type--any) Avoid using `any` type if it is possible. Always create an interface or use an existing one.

    > Why? Because type `any` doesn't tell us anything about the object that you are using. The IDE and the compilator will help you to avoid mistakes, for example, typos or use nonexisting methods/attributes.

    ```javascript
    // bad
    someArray.map((item: any) => item.value);

    // good
    interface Item {
      value: string;
    }
    someArray.map((item: Item) => item.value);
    ```
