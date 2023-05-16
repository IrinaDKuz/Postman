![Картинка](https://learndirectus.com/content/images/2022/03/postman.png)

## HomeWork 1
see [Postman_HW1.postman_collection.json](https://github.com/IrinaDKuz/Postman/blob/main/Postman_HW1.postman_collection.json)
## HomeWork 2
see [Postman_HW2.postman_collection.json](https://github.com/IrinaDKuz/Postman/blob/main/Postman_HW2.postman_collection.json)

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

 Статус код 200
```
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```
 Спарсить response body в json.
 ```
var responseJson = pm.response.json();
Спарсить request.
var request = request.data;
```
 Проверить, что name в ответе равно name s request (name вбить руками.)
```
var myName = "Irina"
pm.test("Check name is " + myName, function () {
 pm.expect(responseJson.name).to.eql(myName);
});
```
 Проверить, что age в ответе равно age s request (age вбить руками.)
```
var myAge = 31
pm.test("Check age is " + myAge, function () {
 pm.expect(+responseJson.age).to.eql(myAge);
});
```
 Проверить, что salary в ответе равно salary s request (salary вбить руками.)
```
var mySalary = 3000
pm.test("Check salary is " + mySalary, function () {
 pm.expect(+responseJson.salary).to.eql(mySalary);
});
```
 Проверить, что name в ответе равно name s request (name забрать из request.)
```
pm.test("Check response.name is equal to request.name", function () {
    pm.expect(responseJson.name).to.eql(request.name);
});
```
 Проверить, что age в ответе равно age s request (age забрать из request.)
```
pm.test("Check response.age is equal to request.age", function () {
    pm.expect(responseJson.age).to.eql(request.age);
});
```
 Проверить, что salary в ответе равно salary s request (salary забрать из request.)
```
pm.test("Check response.salary is equal to request.salary", function () {
    pm.expect(+responseJson.salary).to.eql(+request.salary);
});
```
 Вывести в консоль параметр family из response.
```
console.log(responseJson.family)
```
 Проверить что u_salary_1_5_year в ответе равно salary*4 (salary забрать из request)
```
pm.test("Check response.u_salary_1_5_year is equal to 4*request.salary", function () {
    pm.expect(+responseJson.family.u_salary_1_5_year).to.eql(+request.salary*4);
});
```
### http://162.55.220.72:5005/object_info_3
 Статус код 200
```
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```
 Спарсить response body в json.
```
var responseJson = pm.response.json();
```
 Спарсить request.
```
var request = pm.request.url.query.toObject ();
```
 Проверить, что name в ответе равно name s request (name забрать из request.)
```pm.test("Check response.name is equal to request.name", function () {
    pm.expect(responseJson.name).to.eql(request.name);
});
```
 Проверить, что age в ответе равно age s request (age забрать из request.)
```
pm.test("Check response.age is equal to request.age", function () {
    pm.expect(responseJson.age).to.eql(request.age);
});
```
 Проверить, что salary в ответе равно salary s request (salary забрать из request.)
```
pm.test("Check response.salary is equal to request.salary", function () {
    pm.expect(+responseJson.salary).to.eql(+request.salary);
});
```
 Вывести в консоль параметр family из response.
```
console.log(responseJson.family)
```
 Проверить, что у параметра dog есть параметры name.
```
pm.test("Check that dog have parametr 'name'", function () {
    pm.expect(responseJson.family.pets.dog).to.property("name");
});
```
 Проверить, что у параметра dog есть параметры age.
```
pm.test("Check that dog have parametr 'age'", function () {
    pm.expect(responseJson.family.pets.dog).to.property("age");
```
});
 Проверить, что параметр name имеет значение Luky.
```
pm.test("Check that name is Luky", function () {
    pm.expect(responseJson.family.pets.dog.name).to.eql("Luky");
});
```
 Проверить, что параметр age имеет значение 4.
```
pm.test("Check that age is 4", function () {
    pm.expect(responseJson.family.pets.dog.age).to.eql(4);
});
```

### http://162.55.220.72:5005/object_info_4

 Статус код 200
```
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```
 Спарсить response body в json.
```
var responseJson = pm.response.json();
```
 Спарсить request.
```
var request = pm.request.url.query.toObject ();
```
 Проверить, что name в ответе равно name s request (name забрать из request.)
```
pm.test("Check response.name is equal to request.name", function () {
    pm.expect(responseJson.name).to.eql(request.name);
});
```
 Проверить, что age в ответе равно age из request (age забрать из request.)
```
pm.test("Check response.age is equal to request.age", function () {
    pm.expect(+responseJson.age).to.eql(+request.age);
});
```
 Вывести в консоль параметр salary из request.
```
console.log(request.salary);
```
 Вывести в консоль параметр salary из response.
```
console.log(responseJson.salary);
```
 Вывести в консоль 0-й элемент параметра salary из response.
```
console.log(responseJson.salary[0]);
```
 Вывести в консоль 1-й элемент параметра salary параметр salary из response.
```
console.log(responseJson.salary[1]);
```
 Вывести в консоль 2-й элемент параметра salary параметр salary из response.
```
console.log(responseJson.salary[2]);
```
 Проверить, что 0-й элемент параметра salary равен salary из request (salary забрать из request.)
```
pm.test("Check response.salary[0] is equal to request.salary", function () {
    pm.expect(+responseJson.salary[0]).to.eql(+request.salary);
});
```
 Проверить, что 1-й элемент параметра salary равен salary*2 из reques (salary забрать из request.)
``` pm.test("Check response.salary[1] is equal to request.salary*2", function () {
    pm.expect(+responseJson.salary[1]).to.eql(+2*request.salary);
});
```
 Проверить, что 2-й элемент параметра salary равен salary*3 из request (salary забрать из request.)
```
pm.test("Check response.salary[2] is equal to request.salary*3", function () {
    pm.expect(+responseJson.salary[2]).to.eql(+3*request.salary);
});
```
 Передать в окружение переменную name
```
pm.environment.set("name", responseJson.name);
console.log(pm.environment.get("name"));
```
 Передать в окружение переменную age
```
pm.environment.set("age", responseJson.age);
console.log(pm.environment.get("age"));
```
 Передать в окружение переменную salary
```
pm.environment.set("salary", responseJson.salary);
console.log(pm.environment.get("salary"));
```
 Написать цикл который выведет в консоль по порядку элементы списка из параметра salary.
```
var salary = pm.environment.get("salary");
for (var i = 0; i < salary.length; i++) {
  console.log("Salary " + i + " = " + salary[i]);
}
```

### http://162.55.220.72:5005/user_info_2

 Вставить параметр salary из окружения в request
```
var salary = pm.environment.get("salary");
pm.environment.set("salary_0", salary[0]);
pm.environment.set("salary_1", salary[1]);
pm.environment.set("salary_2", salary[2]);
```
 Вставить параметр age из окружения в age
```
var age = pm.environment.get("age");
```
 Вставить параметр name из окружения в name
```
var name = pm.environment.get("name");
```
 Статус код 200
```
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```
 Спарсить response body в json.
```
var responseJson = pm.response.json();
```
 Спарсить request.
```
var request = pm.request.body.formdata.toObject();
```
 Проверить, что json response имеет параметр start_qa_salary
```
pm.test("Check that response has parametr 'start_qa_salary'", function () {
    pm.expect(responseJson).to.property("start_qa_salary");
});
```
 Проверить, что json response имеет параметр qa_salary_after_6_months
```
pm.test("Check that response has parametr 'qa_salary_after_6_months'", function () {
    pm.expect(responseJson).to.property("qa_salary_after_6_months");
});
```
 Проверить, что json response имеет параметр qa_salary_after_12_months
```
pm.test("Check that response has parametr 'qa_salary_after_12_months'", function () {
    pm.expect(responseJson).to.property("qa_salary_after_12_months");
});
```
 Проверить, что json response имеет параметр qa_salary_after_1.5_year
```
pm.test("Check that response has parametr 'qa_salary_after_1.5_year'", function () {
    pm.expect(responseJson).to.property("qa_salary_after_1.5_year");
});
```
 Проверить, что json response имеет параметр qa_salary_after_3.5_years
```
pm.test("Check that response has parametr 'qa_salary_after_3.5_years'", function () {
    pm.expect(responseJson).to.property("qa_salary_after_3.5_years");
});
```
 Проверить, что json response имеет параметр person
```
pm.test("Check that response has parametr 'person'", function () {
    pm.expect(responseJson).to.property("person");
});
```
 Проверить, что параметр start_qa_salary равен salary из request (salary забрать из request.)
```
pm.test("Check response.start_qa_salary is equal to request.salary", function () {
    pm.expect(+responseJson.start_qa_salary).to.eql(+request.salary);
});
```
 Проверить, что параметр qa_salary_after_6_months равен salary*2 из request (salary забрать из request.)
```
pm.test("Check response.qa_salary_after_6_months is equal to request.salary*2", function () {
    pm.expect(+responseJson.qa_salary_after_6_months).to.eql(+request.salary * 2);
});
```
 Проверить, что параметр qa_salary_after_12_months равен salary*2.7 из request (salary забрать из request.)
```
pm.test("Check response.qa_salary_after_12_months is equal to request.salary*2.7", function () {
    pm.expect(+responseJson.qa_salary_after_12_months).to.eql(+request.salary * 2.7);
});
```
 Проверить, что параметр qa_salary_after_1.5_year равен salary*3.3 из request (salary забрать из request.)
```
pm.test("Check response.qa_salary_after_1.5_year is equal to request.salary*3.3", function () {
    pm.expect(+responseJson["qa_salary_after_1.5_year"]).to.eql(+request.salary * 3.3);
});
```
 Проверить, что параметр qa_salary_after_3.5_years равен salary*3.8 из request (salary забрать из request.)
```
pm.test("Check response.qa_salary_after_3.5_years is equal to request.salary*3.8", function () {
    pm.expect(+responseJson["qa_salary_after_3.5_years"]).to.eql(+request.salary * 3.8);
});
```
 Проверить, что в параметре person, 1-й элемент из u_name равен salary из request (salary забрать из request.)
```
pm.test("Check response.person.u_name[1] is equal to request.salary", function () {
    pm.expect(+responseJson.person.u_name[1]).to.eql(+request.salary);
});
```
 Проверить, что что параметр u_age равен age из request (age забрать из request.)
```
pm.test("Check response.person.u_age is equal to request.age", function () {
    pm.expect(+responseJson.person.u_age).to.eql(+request.age);
});
```
 Проверить, что параметр u_salary_5_years равен salary*4.2 из request (salary забрать из request.)
```
pm.test("Check response.person.u_salary_5_years is equal to request.salary*4.2", function () {
    pm.expect(+responseJson.person.u_salary_5_years).to.eql(+4.2 * request.salary);
});
```
 ***Написать цикл который выведет в консоль по порядку элементы списка из параметра person.
```
var person_values = Object.values(responseJson.person); // Получаем все значения объекта в виде массива
for (var i = 0; i < person_values.length; i++) {
    console.log("" + person_values[i]);
}
```
