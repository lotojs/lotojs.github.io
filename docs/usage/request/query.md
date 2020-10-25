# @Query

The **@Query** decorator will assign to a variable the data set in **'req.query'** for use in the function.  The value of this data refers to the **'query of the path'**.

```js
@Controller()
export class MyController{

    @Get("/test")
    async test(
        @Query()
        query : any
    ){
        ...
    }

}
```
