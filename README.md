# Postman
## HomeWork 1
see Postman_HW1.postman_collection.json
## HomeWork 2
// Статус код 200
```
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```
// Проверить, что в body приходит правильный string.
```
pm.test("Body is correct", function () {
    pm.response.to.have.body("This is the first responce from server!ss");
});
```