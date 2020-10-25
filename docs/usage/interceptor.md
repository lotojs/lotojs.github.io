# @Interceptor

The @Interceptor decorator will allow the capture of any exception that could occur in the flow.

```js
@Controller()
export class MyController { 

    @Interceptor([middleware])
    @Get("/test")
    async index(){
        ...
    }

}
```
#### Options

<div style="padding-left: 10px">

- **middleware \<Function\>:** The natural function that will be executed on any exception. <br>
The composition of the function is as follows ...
```js
function(req : RequestAction, res : ResponseAction, exception : any) => {
    ...
}
```
Where:
 - **req:** Reference to 'req' object of express
 - **res:** Reference to 'res' object of express
 - **exception:** Instance of exception

</div>
