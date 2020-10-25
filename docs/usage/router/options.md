# @Options

The **@Options** decorator will allow processing only OPTIONS type requests, this must be entered in a function of the controller class.


```js
@Controller()
export class MyController { 

    @Options([path])
    async index(){
        ...
    }

}
```

#### Options \<String\>

<div style="padding-left: 10px">

- **path:** Define path for the endpoint

</div>