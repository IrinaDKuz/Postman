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
salary.forEach(salary => console.log(salary)); 
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
## HomeWork 3
see [Postman_HW3.postman_collection.json](https://github.com/IrinaDKuz/Postman/blob/main/Postman_HW3.postman_collection.json)
### http://162.55.220.72:5005/login
Приходящий токен необходимо передать во все остальные запросы.
```
pm.environment.set("token", pm.response.json().token);
```
### http://162.55.220.72:5005/user_info
Статус код 200
```
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```
Проверка структуры json в ответе.
https://www.liquid-technologies.com/online-json-to-schema-converter
```
var response = pm.response.json();
var schema = {  
  "type": "object",
  "properties": {
    "person": {
      "type": "object",
      "properties": {
        "u_age": {
          "type": "integer"
        },
        "u_name": {
          "type": "array",
          "items": [
            {
              "type": "string"
            },
            {
              "type": "integer"
            },
            {
              "type": "integer"
            }
          ]
        },
        "u_salary_1_5_year": {
          "type": "integer"
        }
      },
      "required": [
        "u_age",
        "u_name",
        "u_salary_1_5_year"
      ]
    },
    "qa_salary_after_12_months": {
      "type": "number"
    },
    "qa_salary_after_6_months": {
      "type": "integer"
    },
    "start_qa_salary": {
      "type": "integer"
    }
  },
  "required": [
    "person",
    "qa_salary_after_12_months",
    "qa_salary_after_6_months",
    "start_qa_salary"
  ]
}
pm.test('Schema is valid', function () {
pm.response.to.have.jsonSchema(schema);
});
```
В ответе указаны коэффициенты умножения salary, напишите тесты по проверке правильности результата перемножения на коэффициент.
```
var request = JSON.parse(pm.request.body.raw);
pm.test("Check response.u_salary_1_5_year is equal to 4 * request.salary", function () {
    pm.expect(+response.person.u_salary_1_5_year).to.eql(+request.salary * 4);
});

pm.test("Check response.qa_salary_after_12_months is equal to 2.9 * request.salary", function () {
    pm.expect(+response.qa_salary_after_12_months).to.eql(+request.salary * 2.9);
});

pm.test("Check response.qa_salary_after_6_months is equal to 2 * equest.salary", function () {
    pm.expect(+response.qa_salary_after_6_months).to.eql(+request.salary * 2);
});
```
Достать значение из поля 'u_salary_1.5_year' и передать в поле salary запроса http://162.55.220.72:5005/get_test_user
```
var u_salary_1_5_year = response.person.u_salary_1_5_year;
pm.environment.set('u_salary_1_5_year', u_salary_1_5_year);
```
### http://162.55.220.72:5005/get_test_user
Достать значение из поля 'u_salary_1.5_year' и передать в поле salary запроса http://162.55.220.72:5005/get_test_user
```
console.log(pm.environment.get("u_salary_1_5_year"));
```
### http://162.55.220.72:5005/new_data
Статус код 200
```
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```

Проверка структуры json в ответе.
```
var response = pm.response.json();
var schema = {
  "type": "object",
  "properties": {
    "age": {
      "type": "integer"
    },
    "name": {
      "type": "string"
    },
    "salary": {
      "type": "array",
      "items": [
        {
          "type": "integer"
        },
        {
          "type": "string"
        },
        {
          "type": "string"
        }
      ]
    }
  },
  "required": [
    "age",
    "name",
    "salary"
  ]
}
    
pm.test('Schema is valid', function () {
pm.response.to.have.jsonSchema(schema);
});
```
В ответе указаны коэффициенты умножения salary, напишите тесты по проверке правильности результата перемножения на коэффициент.
```
var request = pm.request.body.formdata.toObject();
pm.test("Check response.salary[1] is equal to 2 * request.salary", function () {
 pm.expect(+response.salary[1]).to.eql(+request.salary * 2);
});

pm.test("Check response.salary[2] is equal to 3 * request.salary", function () {
 pm.expect(+response.salary[2]).to.eql(+request.salary * 3);
});
```
Проверить, что 2-й элемент массива salary больше 1-го и 0-го
```
pm.test("Check response.salary[2] is greater than the [0] and [1] ", function () {
 pm.expect(+response.salary[2] >= +response.salary[0]
  && +response.salary[2] >= +response.salary[0]);
});
```
### http://162.55.220.72:5005/test_pet_info
Статус код 200
```
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```
Проверка структуры json в ответе.
```
var response = pm.response.json();
var schema = {
  "type": "object",
  "properties": {
    "age": {
      "type": "integer"
    },
    "daily_food": {
      "type": "number"
    },
    "daily_sleep": {
      "type": "number"
    },
    "name": {
      "type": "string"
    }
  },
  "required": [
    "age",
    "daily_food",
    "daily_sleep",
    "name"
  ]
}
pm.test('Schema is valid', function () {
pm.response.to.have.jsonSchema(schema);
});
```
В ответе указаны коэффициенты умножения weight, напишите тесты по проверке правильности результата перемножения на коэффициент.
```
var request = pm.request.body.formdata.toObject();
pm.test("Check response.daily_food is equal to 0.012 * request.weight", function () {
 pm.expect(+response.daily_food).to.eql(+request.weight * 0.012);
});

pm.test("Check response.daily_sleep is equal to 2.5 * request.weight", function () {
 pm.expect(+response.daily_sleep).to.eql(+request.weight *  2.5);
});
```
### http://162.55.220.72:5005/get_test_user
Статус код 200
```
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```
Проверка структуры json в ответе.
```
var response = pm.response.json();
var schema = {
  "type": "object",
  "properties": {
    "age": {
      "type": "string"
    },
    "family": {
      "type": "object",
      "properties": {
        "children": {
          "type": "array",
          "items": [
            {
              "type": "array",
              "items": [
                {
                  "type": "string"
                },
                {
                  "type": "integer"
                }
              ]
            },
            {
              "type": "array",
              "items": [
                {
                  "type": "string"
                },
                {
                  "type": "integer"
                }
              ]
            }
          ]
        },
        "u_salary_1_5_year": {
          "type": "integer"
        }
      },
      "required": [
        "children",
        "u_salary_1_5_year"
      ]
    },
    "name": {
      "type": "string"
    },
    "salary": {
      "type": "integer"
    }
  },
  "required": [
    "age",
    "family",
    "name",
    "salary"
  ]
}
pm.test('Schema is valid', function () {
pm.response.to.have.jsonSchema(schema);
});
```
Проверить что значение поля name = значению переменной name из окружения
```
var request = pm.request.body.formdata.toObject();
pm.environment.set("name", request.name);

pm.test("Check response.name is equal to environment.name", function () {
 pm.expect(response.name).to.eql(pm.environment.get("name"));
});
```
Проверить что занчение поля age в ответе соответсвует отправленному в запросе значению поля age
```
pm.test("Check response.age is equal to request.age", function () {
 pm.expect(+response.age).to.eql(+request.age);
});
```
### http://54.157.99.22:80/currency
Взять любой объект из присланного списка, используя js random.
В объекте взять Cur_ID и передать через окружение в следующий запрос.
```
var response = pm.response.json();
var randomObject = response[Math.floor(Math.random() * response.length)];
pm.environment.set("Cur_ID", randomObject.Cur_ID);
```
*** Получить список валют, итерировать список валют в каждой итерации отправлять запрос на сервер для получения курса каждой валюты если возвращается 500 код, переходим к следующей итреации
 если получаем 200 код, проверяем response json на наличие поля "Cur_OfficialRate"
 если поле есть, пишем в консоль инфу про фалюту в виде response
```
var env_token = pm.environment.get("token");

for(let i = 0; i < response.length - 1 ; i++){
   cur_ID = (response[i].Cur_ID);
   sendPostRequest(cur_ID);
};

function sendPostRequest(cur_ID){
var options = {
    url: 'http://54.157.99.22:80/curr_byn',
    method: 'POST',
    header: {
      'Content-Type': 'application/json'
    },
    body: {
    mode: 'formdata',
    formdata:  [
  { key: 'auth_token', value: env_token },
  { key: 'curr_code', value: cur_ID }
],
}
}
// Обработка ответа
pm.sendRequest(options, function (err, response) {
{
    "Cur_Abbreviation": str
    "Cur_ID": int,
    "Cur_Name": str,
    "Cur_OfficialRate": float,
    "Cur_Scale": int,
    "Date": str
}
 переходим к следующей итерации */
    console.log("It's status code: " + response.code);
        if (response.code === 500) {
        }
		if (response.code === 200) {
			if (response.json().hasOwnProperty("Cur_OfficialRate")) 
                console.log(response.json());
            }
  });
}
```
### http://54.157.99.22:80/curr_byn