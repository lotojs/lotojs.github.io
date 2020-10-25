# Pipe

With the **Pipe** function it will be possible to create a flow of **input and output** that will allow the middleware to obtain reference to those data that have been previously processed.

> Can be used in **Input and Output**.

```js
@Controller()
export class MyController { 

    @Input(Pipe([[middleware]...]))
    @Get("/test")
    async index(){
        ...
    }

}
```

#### Options \<Function | Middleware\>

<div style="padding-left: 10px">

- **middleware:** The natural function or class that implements the ['Middleware interface']() that will be executed on the input of the request. <br>
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

</div>

#### Example

```js
@Controller()
export class MyController { 

    @Input(
        Pipe[
            (req, res, next, context) => {
                next();
                return 'Hello';
            },
            (req, res, next, context) => {
                const input = context.input;
                next();
                return input + ' World';
            },
            (req, res, next, context) => {
                const input = context.input;
                // Process the string 'Hello World' ...
                next();
            }
        ]
    )
    @Get("/test")
    async index(){
        ...
    }

}
```