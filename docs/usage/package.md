# @Package

The **@Package** decorator will allow to establish a class as a **'package'** that will be the entry points for the correct operation of the controllers and the corresponding routes.

```js
@Package([options])
export class MyPackage {}
```

#### Options

<div style="padding-left: 10px">

- **base \<string\>:** Global prefix path for all routes in all controllers
- **controllers \<array\>:** Array of controllers.
- **inputs \<array\>:** Array of inputs middlewares for all routes in all controllers (has a predecessor order)
- **outputs \<array\>:** Array of outputs middlewares for all routes in all controllers (has a predecessor order)
- **interceptor \<function\>:** Global interceptor for all routes in all controllers
- **inherits \<array\>:** Array of packages where their properties will be inherited. (mix properties)
- **joins \<array\>:** Join the references of packages (does not mix properties)

</div>