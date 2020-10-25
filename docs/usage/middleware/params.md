# Params

With the **Params** function you will be able to pass some kind of configuration that the middleware needs for a different operation depending on the occasion.

> Can be used in **Input and Output**.

```js
@Controller()
export class MyController { 

    @Input(Params([middleware], [params]))
    @Get("/test")
    async test(){
        ...
    }

}
```

#### Options

<div style="padding-left: 10px">

- **middleware \<function | Middleware\>:** The natural function or class that implements the ['Middleware interface']() that will be executed on the input of the request. <br>
The composition of the function is as follows ...
```js
function(req : RequestAction, res : ResponseAction, next : () => void, context : ContextRoute) => {
    ...
}
```
Where:
 - **req:** Reference to 'req' object of express
 - **res:** Reference to 'res' object of express
 - **next:** Execute the next input
 - **context:** Reference to the work context in the flow

- **params \<any\>:** The value to be passed to the middleware.

</div>

#### Example

```js
@Controller()
export class MyController { 

    @Input(
        Params(
            (req, res, next, context) => {
                const params = context.params;
                // Process params.max ...
                next();
            },
            {
                max: 10
            }
        )
    )
    @Get("/test")
    async test(){
        ...
    }

}
```
