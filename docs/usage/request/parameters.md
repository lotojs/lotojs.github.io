# @Parameters

The **@Parameters** decorator will assign to a variable the data set in **'req.params'** for use in the function.  The value of this data refers to the **'params of the path'**.

```js
@Controller()
export class MyController{

    @Get("/test/:id")
    async test(
        @Parameters()
        params : any
    ){
        ...
    }

}
```
