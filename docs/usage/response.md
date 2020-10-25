# @Response

The **@Response** decorator will assign to a variable the data set in **'res'**, this will give access to make the desired response to the client.

```js
@Controller()
export class MyController{

    @Get("/test")
    async test(
        @Response()
        res : any
    ){
        ...
    }

}
```
