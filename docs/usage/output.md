# @Output

The @Output decorator allows to execute functions after the function containing the found path has been executed, this can be used for example: rendering an object, saving records, etc.

> It has support for middleware with operation for **express**.

> The order of use of **Output** is maintained for the execution flow.

```js
@Controller()
export class MyController { 

    @Output([middleware])
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
 - **next:** Execute the next output
 - **context:** Reference to the work context in the flow

</div>
