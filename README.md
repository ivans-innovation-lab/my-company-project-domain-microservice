# [projects](http://ivans-innovation-lab.github.io/projects)/my-company-project-domain-microservice [![CircleCI](https://circleci.com/gh/ivans-innovation-lab/my-company-project-domain-microservice.svg?style=svg)](https://circleci.com/gh/ivans-innovation-lab/my-company-project-domain-microservice)

## Running instructions

Run RabbitMQ
```
$ brew services start rabbitmq
```

Make sure that services are running:

 - [my-company-configuration-backingservice](https://github.com/ivans-innovation-lab/my-company-configuration-backingservice)
 - [my-company-registry-backingservice](https://github.com/ivans-innovation-lab/my-company-registry-backingservice) 
 
Make sure that you have this libraries installed in your local maven repsoitory:

 - [my-company-common (transient dependency)](https://github.com/ivans-innovation-lab/my-company-common)
 - [my-company-project-domain](https://github.com/ivans-innovation-lab/my-company-project-domain)

```bash
$ cd my-company-project-domain-microservice
$ ./mvnw spring-boot:run
```

Application will be available on port 8082 (http://localhost:8082)

## Explore

### curl

```
$ curl -H "Content-Type: application/json" -X POST -d '{"name":"Name","repoUrl":"URL","siteUrl": "siteUrl","description": "sdfsdfsdf"}' http://127.0.0.1:8082/projectcommands 
```

### rambittmq

Open RabbitMQ management web console at http://localhost:15672/ and explore exchanges, queues and messages.

### registry backing service

Open Registry (Eureka) web console at http://localhost:8761/ and find 'my-company-project-domain-microservice' registered.

