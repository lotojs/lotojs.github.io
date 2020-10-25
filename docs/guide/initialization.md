# Initialization

### With Server

In the main file of your project , use this basic code ...

```js
const myapp = App.init(
    [packages ...],
);
const http = myapp.http({options});
http.listen(3000);
```

### Without Server

In the main file of your project , use this basic code ...

```js
const myapp = App.init(
    [packages ...],
);
// const referenceToExpress = myapp.app;
```