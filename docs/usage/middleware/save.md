# Save

With the **Save** function you can save the return value of the middleware to later be used within the Input and Output flows and within the same function of the found path.

> Can be used in **Input and Output**.

```js
@Controller()
export class MyController { 

    @Input(Save([middleware], [key]))
    @Get("/test")
    async index(){
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

- **key \<string\>:** The name of the key where the return value will be saved.

</div>

#### Example

```js
@Controller()
export class MyController { 

    @Input(
        Save(
            (req, res, next, context) => {
                next();
                return 'Hello';
            },
            'mymessage'
        )
    )
    @Get("/test")
    async index(){
        ...
    }

}
```

> See [Obtain]() and [ContextSave]() to get the saved value.
