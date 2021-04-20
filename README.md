## BizCover.Api.Cars
This repository has been developed by Afshin Teymoori
Includes the restful api which has two controllers 
## 1. Cars 
- Cars controller include Get, Post and Put methods for getting all cars or by id, Insert a new car and Update an existing car respectively. 

## 2. Baskets
- Basket includs a shopping basket of cars that the user should can create and get the **Discount** for.
- it included Get, Post, Delete and Get/{id}/discount for getting, creating, deleting and getting the basket discount respectively.
- Discounts will be calculated based on the rules.
- for example to add a new basket you should do a Post request to https://localhost:5081/baskets and the body of post request is an array of carIds that you want to include in the basket like [1,2,5] will create a basket with 3 cars with ids 1, 2,and 5. 

## Implementing the rules

1. I have userd Strategy pattern to implement the rules. This way, adding new rules is as easy as implementing **IDiscountStrategy interface** and registering the new class in the startup.cs DI configuration method.

#### Tests
- I have developed two test projecs, one for Integration tests and the other for Unit/Component tests.
- Integration tests are in **BizCover.Api.Cars.Integration.Tests** project and each tests will have it own TestContext class and corresponding Api. Effectively, these tests are end-to-end tests.
- Unit tests are in **BizCover.Api.Cars.Tests** and are more of component tests as opposed to focusing an a single method of a class. In these tests I have Stubbed out the dependecies.

#### Build and Run

- You can open the solution file in the root of the repo in visual studio and build it 
- You can also see swagger index page to test all the endpoints https://localhost:5081/swagger/index.html
- I have also exported the postman collection in the Docs folder of the root repo

