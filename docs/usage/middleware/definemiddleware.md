# @DefineMiddleware

There is also the possibility of creating a middleware using a 'class' instead of a pure function, for this the decorator **@DefineMiddleware** is used implementing the **Middleware** interface.

```js
@DefineMiddleware([options])
export class MyMiddleware implements Middleware { 

    async function middleware(
        req : RequestAction, 
        res : ResponseAction, 
        next : () => void, 
        context : ContextRoute
    ){
        ...
    }

}
```

#### Options

<div style="padding-left: 10px">

- **pattern \<MiddlewarePattern\>:** Pattern to be used for initialization. **Default: Singleton**

</div>