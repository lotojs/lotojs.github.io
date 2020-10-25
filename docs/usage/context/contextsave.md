# @ContextSave

With the **@ContextSave** function we will be able to obtain the saved data from the flow in the same way as the **Obtain** function, however **@ContextSave** can only be used within the function of the path found.

```js
@Controller()
export class MyController { 

    @Input(...))
    @Get("/test")
    async test(
        @ContextSave([key])
        data : any
    ){
        ...
    }

}
```

#### Options

<div style="padding-left: 10px">

- **key \<string\>:** Name of saved key.

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
    async test(
        @ContextSave('mymessage)
        data : any
    ){
        ...
    }

}
```
