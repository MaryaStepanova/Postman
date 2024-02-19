## Postman_Homework_2
___

http://162.55.220.72:5005/first
1. Отправить запрос.
2. Статус код 200
```
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```
3. Проверить, что в body приходит правильный string.
```
pm.test("Body matches string", function () {
    var responseText = pm.response.text();
    pm.expect(responseText).to.be.a("string");
});
```

http://162.55.220.72:5005/user_info_3
1. Отправить запрос.
2. Статус код 200
```
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```
3. Спарсить response body в json.
```
var responseJson = pm.response.json();
```
4. Проверить, что name в ответе равно name s request (name вбить руками.)
```
pm.test("Check name", function (){
    pm.expect(responseJson.name).to.eql("Anna");
});
```
5. Проверить, что age в ответе равно age s request (age вбить руками.)
```
pm.test("Check age", function (){
    pm.expect(+responseJson.age).to.eql(30);
});
```
6. Проверить, что salary в ответе равно salary s request (salary вбить руками.)
```
pm.test("Check salary", function (){
    pm.expect(+responseJson.salary).to.eql(1000);
});
```
7. Спарсить request.
```
var requestBody = request.data;
```
8. Проверить, что name в ответе равно name s request (name забрать из request.)
```
pm.test("Name from response equals name from request", function (){
    pm.expect(responseJson.name).to.eql(requestBody.name);
});
```
9. Проверить, что age в ответе равно age s request (age забрать из request.)
```
pm.test("Age from response equals age from request", function (){
    pm.expect(responseJson.age).to.eql(requestBody.age);
});
```
10. Проверить, что salary в ответе равно salary s request (salary забрать из request.)
```
pm.test("Salary from response equals salary from request", function (){
    pm.expect(responseJson.salary).to.eql(+requestBody.salary);
});
```
11. Вывести в консоль параметр family из response.
```
console.log(responseJson.family);
```
12. Проверить что u_salary_1_5_year в ответе равно salary*4 (salary забрать из request)
```
pm.test("Salary in 4 years from response equals salary*4", function (){
	pm.expect(responseJson.family.u_salary_1_5_year).to.eql(requestBody.salary * 4);
});
```

http://162.55.220.72:5005/object_info_3
1. Отправить запрос.
2. Статус код 200
```
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```
3. Спарсить response body в json.
```
var responseJson = pm.response.json();
```
4. Спарсить request.
```
var requestData = pm.request.url.query.toObject();
```
5. Проверить, что name в ответе равно name s request (name забрать из request.)
```
pm.test("Name from response equals name from request", function (){
    pm.expect(responseJson.name).to.eql(requestData.name);
});
```
6. Проверить, что age в ответе равно age s request (age забрать из request.)
```
pm.test("Age from response equals age from request", function (){
    pm.expect(responseJson.age).to.eql(requestData.age);
});
```
7. Проверить, что salary в ответе равно salary s request (salary забрать из request.)
```
pm.test("Salary from response equals salary from request", function (){
    pm.expect(responseJson.salary).to.eql(+requestData.salary);
});
```
8. Вывести в консоль параметр family из response.
```
console.log(responseJson.family);
```
9. Проверить, что у параметра dog есть параметры name.
```
pm.test("Dog parameter has a name", function(){
    pm.expect(responseJson.family.pets.dog).to.have.property("name");
});
```
10. Проверить, что у параметра dog есть параметры age.
```
pm.test("Dog parameter has an age", function(){
    pm.expect(responseJson.family.pets.dog).to.have.property("age");
});
```
11. Проверить, что параметр name имеет значение Luky.
```
pm.test("Dog name equals Luky", function(){
    pm.expect(responseJson.family.pets.dog.name).to.eql("Luky");
});
```
12. Проверить, что параметр age имеет значение 4.
```
pm.test("Dog age equals 4", function(){
    pm.expect(+responseJson.family.pets.dog.age).to.eql(4);
});
```

http://162.55.220.72:5005/object_info_4
1. Отправить запрос.
2. Статус код 200
```
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```
3. Спарсить response body в json.
```
var responseJson = pm.response.json();
```
4. Спарсить request.
```
var requestData = pm.request.url.query.toObject();
```
5. Проверить, что name в ответе равно name s request (name забрать из request.)
```
pm.test("Name from response equals name from request", function (){
    pm.expect(responseJson.name).to.eql(requestData.name);
});
```
6. Проверить, что age в ответе равно age из request (age забрать из request.)
```
pm.test("Age from response equals age from request", function (){
    pm.expect(responseJson.age).to.eql(+requestData.age);
});
```
7. Вывести в консоль параметр salary из request.
```
console.log(requestData.salary);
```
8. Вывести в консоль параметр salary из response.
```
console.log(responseJson.salary);
```
9. Вывести в консоль 0-й элемент параметра salary из response.
```
console.log("0 element of salary from response",responseJson.salary[0]);
```
10. Вывести в консоль 1-й элемент параметра salary параметр salary из response.
```
console.log("1 element of salary from response",responseJson.salary[1]);
```
11. Вывести в консоль 2-й элемент параметра salary параметр salary из response.
```
console.log("2 element of salary from response",responseJson.salary[2]);
```
12. Проверить, что 0-й элемент параметра salary равен salary из request (salary забрать из request.)
```
pm.test("0 element of salary equals salary from request", function (){
    pm.expect(responseJson.salary[0]).to.eql(+requestData.salary);
});
```
13. Проверить, что 1-й элемент параметра salary равен salary*2 из request (salary забрать из request.)
```
pm.test("1 element of salary equals salary*2 from request", function (){
    pm.expect(+responseJson.salary[1]).to.eql(requestData.salary*2);
});
```
14. Проверить, что 2-й элемент параметра salary равен salary*3 из request (salary забрать из request.)
```
pm.test("2 element of salary equals salary*3 from request", function (){
    pm.expect(+responseJson.salary[2]).to.eql(requestData.salary*3);
});
```
15. Создать в окружении переменную name
16. Создать в окружении переменную age
17. Создать в окружении переменную salary
18. Передать в окружение переменную name
```
pm.environment.set("name", requestData.name);
```
19. Передать в окружение переменную age
```
pm.environment.set("age", requestData.age);
```
20. Передать в окружение переменную salary
```
pm.environment.set("salary", requestData.salary);
```
21. Написать цикл который выведет в консоль по порядку элементы списка из параметра salary.
```
for (var i = 0; i < responseJson.salary.length; i++) {
	console.log(responseJson.salary[i]);
};
```

http://162.55.220.72:5005/user_info_2
1. Вставить параметр salary из окружения в request
2. Вставить параметр age из окружения в age
3. Вставить параметр name из окружения в name
4. Отправить запрос.
5. Статус код 200
```
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```
6. Спарсить response body в json.
```
var responseJson = pm.response.json();
```
7. Спарсить request.
```
var requestBody = request.data;
```
8. Проверить, что json response имеет параметр start_qa_salary
```
pm.test("Проверить, что json response имеет параметр start_qa_salary", function () {
    pm.expect(responseJson).to.have.property("start_qa_salary");
});
```
9. Проверить, что json response имеет параметр qa_salary_after_6_months
```
pm.test("Проверить, что json response имеет параметр qa_salary_after_6_months", function () {
    pm.expect(responseJson).to.have.property("qa_salary_after_6_months");
});
```
10. Проверить, что json response имеет параметр qa_salary_after_12_months
```
pm.test("Проверить, что json response имеет параметр qa_salary_after_12_months", function () {
    pm.expect(responseJson).to.have.property("qa_salary_after_12_months");
});
```
11. Проверить, что json response имеет параметр qa_salary_after_1.5_year
```
pm.test("Проверить, что json response имеет параметр qa_salary_after_1.5_year", function () {
    pm.expect(responseJson).to.have.property("qa_salary_after_1.5_year");
});
```
12. Проверить, что json response имеет параметр qa_salary_after_3.5_years
```
pm.test("Проверить, что json response имеет параметр qa_salary_after_3.5_years", function () {
    pm.expect(responseJson).to.have.property("qa_salary_after_3.5_years");
});
```
13. Проверить, что json response имеет параметр person
```
pm.test("Response has person parametr", function () {
    pm.expect(responseJson).to.have.property("person");
});
```
14. Проверить, что параметр start_qa_salary равен salary из request (salary забрать из request.)
```
pm.test("start_qa_salary equals salary from request", function (){
    pm.expect(responseJson.start_qa_salary).to.eql(+requestBody.salary);
});
```
15. Проверить, что параметр qa_salary_after_6_months равен salary*2 из request (salary забрать из request.)
```
pm.test("qa_salary_after_6_months equals salary from request", function (){
    pm.expect(+responseJson.qa_salary_after_6_months).to.eql(requestBody.salary*2);
});
```
16. Проверить, что параметр qa_salary_after_12_months равен salary*2.7 из request (salary забрать из request.)
```
pm.test("qa_salary_after_12_months equals salary from request", function (){
    pm.expect(+responseJson.qa_salary_after_12_months).to.eql(requestBody.salary*2.7);
});
```
17. Проверить, что параметр qa_salary_after_1.5_year равен salary*3.3 из request (salary забрать из request.)
```
pm.test("qa_salary_after_1.5_year equals salary from request", function (){
    pm.expect(+responseJson['qa_salary_after_1.5_year']).to.eql(requestBody.salary*3.3);
});
```
18. Проверить, что параметр qa_salary_after_3.5_years равен salary*3.8 из request (salary забрать из request.)
```
pm.test("qa_salary_after_3.5_years equals salary from request", function (){
    pm.expect(+responseJson['qa_salary_after_3.5_years']).to.eql(requestBody.salary*3.8);
});
```
19. Проверить, что в параметре person, 1-й элемент из u_name равен salary из request (salary забрать из request.)
```
pm.test("1 element of u_name equals salary from request", function (){
    pm.expect(responseJson.person.u_name[1]).to.eql(+requestBody.salary);
});
```
20. Проверить, что что параметр u_age равен age из request (age забрать из request.)
```
pm.test("u_age equals age from request", function (){
    pm.expect(responseJson.person.u_age).to.eql(+requestBody.age);
});
```
21. Проверить, что параметр u_salary_5_years равен salary*4.2 из request (salary забрать из request.)
```
pm.test("u_salary_5_years equals salary*4.2 from request", function (){
    pm.expect(responseJson.person.u_salary_5_years).to.eql(+requestBody.salary*4.2);
});
```
22. ***Написать цикл который выведет в консоль по порядку элементы списка из параметра person.
```
for (const key in responseJson.person) {
    console.log(`${key}: ${responseJson.person[key]}`);
}
```

