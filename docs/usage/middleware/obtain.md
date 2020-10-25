# Obtain

With the **Obtain** function you can obtain the value of some data saved by using the Save function.

> Can be used in **Input and Output**.

```js
@Controller()
export class MyController { 

    @Input(Obtain([key]))
    @Get("/test")
    async test(){
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
    @Input(
        Pipe(
            [
                Obtain('mymessage'),
                (req, res, next, context) => {
                    const input = context.input // 'Hello'
                    // Process input ..
                    next();
                }
            ]
        )
    )
    @Get("/test")
    async test(){
        ...
    }

}
```
