# MicroServices : Hello World !
### Basics of microservices architecture w/ Spring Cloud
The following project aims to create two single projects depending on each other as a first step, and then the purpose is to have an application with many services communicating following the microservices' architecture.

While READingME, you will find the steps that I followed during the creation till the containerisation of those microservices.
1. Create two services : Customer & Billing services
    The two Spring Boot applications are generally basics. Each microservice has its DAO, business, service and web layers. The structure of those projects is represented like the following :
   ![Customer-service_structure](https://github.com/loubnaAminou/MicroServices/blob/main/imgs/structure_customer.png)
![Billing-service_structure](https://github.com/loubnaAminou/MicroServices/blob/main/imgs/structure_billing.png)

2. 