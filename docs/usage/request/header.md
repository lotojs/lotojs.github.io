# @Header

The **@Header** decorator will assign to a variable the data set in **'req.headers'** for use in the function.  The value of this data refers to the **'request header'**.

```js
@Controller()
export class MyController{

    @Get("/test")
    async test(
        @Header()
        headers : any
    ){
        ...
    }

}
```
