![Картинка](https://learndirectus.com/content/images/2022/03/postman.png)

## HomeWork 1
see [Postman_HW1.postman_collection.json] (https://github.com/IrinaDKuz/Postman/blob/main/Postman_HW1.postman_collection.json)
## HomeWork 2
see [Postman_HW2.postman_collection.json] (https://github.com/IrinaDKuz/Postman/blob/main/Postman_HW2.postman_collection.json)

### http://162.55.220.72:5005/first
 Статус код 200
```
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```
 Проверить, что в body приходит правильный string.
```
pm.test("Body is correct", function () {
    pm.response.to.have.body("This is the first responce from server!ss");
});
```
### http://162.55.220.72:5005/user_info_3
