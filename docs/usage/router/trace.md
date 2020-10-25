# @Trace

The **@Trace** decorator will allow processing only TRACE type requests, this must be entered in a function of the controller class.


```js
@Controller()
export class MyController { 

    @Trace([path])
    async index(){
        ...
    }

}
```

#### Options \<String\>

<div style="padding-left: 10px">

- **path:** Define path for the endpoint

</div>