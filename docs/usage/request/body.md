# @Body

The **@Body** decorator will assign to a variable the data set in **'req.body'** for use in the function.  The value of this data refers to the **'request body'**.

```js
@Controller()
export class MyController{

    @Post("/test")
    async test(
        @Body()
        body : any
    ){
        ...
    }

}
```
