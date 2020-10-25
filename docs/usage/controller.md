# @Controller

The controller will allow the handling of connections by the clients, that is, a class declared with the **@Controller** decorator will process the routes established in it.

```js
@Controller([options])
export class MyController { ... }
```

#### Options \<Object\>

<div style="padding-left: 10px">

- **path:** Global prefix path for all routes in the controller

</div>