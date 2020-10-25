# @Request

The **@Request** decorator will assign to a variable the data set in **'req'**, this will give access to process the client's request.

```js
@Controller()
export class MyController{

    @Get("/test")
    async test(
        @Request()
        req : any
    ){
        ...
    }

}
```
