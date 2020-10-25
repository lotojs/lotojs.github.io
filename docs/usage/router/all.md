# @All

The **@All** decorator will allow processing all **http request methods**, this must be entered in a function of the controller class.


```js
@Controller()
export class MyController { 

    @All([path])
    async index(){
        ...
    }

}
```

#### Options \<String\>

<div style="padding-left: 10px">

- **path:** Define path for the endpoint

</div>