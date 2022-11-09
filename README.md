# MicroServices : Hello World !
### Basics of microservices architecture w/ Spring Cloud
The following project aims to create two single projects depending on each other as a first step, and then the purpose is to have an application with many services communicating following the microservices' architecture.

While READingME, you will find the steps that I followed during the creation till the containerisation of those microservices.
1. Create two services : Customer & Billing services
    The two Spring Boot applications are generally basics. Each microservice has its DAO, business and web layers. The structure of those projects is represented like the following :
   ![Customer-service_structure](https://github.com/loubnaAminou/MicroServices/blob/main/imgs/structure_customer.png)
![Billing-service_structure](https://github.com/loubnaAminou/MicroServices/blob/main/imgs/structure_billing.png)

2. Test the APIs using SWAGGER3 (Open API)
    As usual, after the creation of the multiple layers of a Spring Application, the next step is to test the connection to the APIs through several tools. In this case, we will use Swagger3 as an Open API Documentation, and try to check if the HTTP methods works on successfully.

![Customer-API](https://github.com/loubnaAminou/MicroServices/blob/main/imgs/swagger-customer.png)

![Billing-API](https://github.com/loubnaAminou/MicroServices/blob/main/imgs/swagger-billing.png)
   
Let's test those APIs by executing one of the methods. For the customer API, I will add new customer named "C03". And I will show the invoices for the customers.
![Customer-testAPI](https://github.com/loubnaAminou/MicroServices/blob/main/imgs/testapi_customer.png)
![Billing-testAPI](https://github.com/loubnaAminou/MicroServices/blob/main/imgs/testapi_billing.png)


3. Create the communication between microservices by OpenFeign

    In this project, we have two microservices communicating with each other. More specifically, the billing service needs more pieces of information from the customer service in order to identify the customer who the bill belongs for him. That's why, we have to use Spring Cloud OpenFeign as a tool to make web services easier. How can we use OpenFeign ? is by creating a REST client interface which we could specify the services that we would to consume.In our case, we will create a REST client interface for the customer service to receive the customers.

![OpenFeignInterface](https://github.com/loubnaAminou/MicroServices/blob/main/imgs/openfeign.png)


4. Create The spring Cloud Gateway
5. Create the Eureka Service
6. Containerize microservices using Docker
Thanks to the containerisation in Docker, we will never struggle with the 4 running instances of IntelliJ projects at the same time. The creation of containers deploying microservices facilitates the use of such a huge architecture. And when we talk about microservices means multiple applications then several containers, so we have to use docker compose in order to configure all the services through its configuration. So, the configuration of the microservices is defined in [docker-compose.yaml](https://github.com/loubnaAminou/MicroServices/blob/main/docker-compose/docker-compose.yaml). And as a result, we have 4 containers for 4 microservices :
   ![docker-containers](https://github.com/loubnaAminou/MicroServices/blob/main/imgs/docker-containers.png)
