# Spring Cloud Eureka Discovery Server  

This project is a **Eureka Discovery Server** built in Spring Cloud, designed to manage service registration and discovery
in a distributed system. It is ideal for microservices environments, facilitating seamless service communication

## Features  

- **Eureka server** for service registration and discovery 
- Configured for `Docker` environment with `host.docker.internal` as the hostname  
- **Actuator endpoints** to monitor the server health and information
- Use **Spring Cloud 2023.0.3** and **Java 21**

## Configuration  

### Application properties  

```yaml
server.port: 8761
spring.application.name: spring-cloud-discovery
eureka:
  instance:
    hostname: host.docker.internal
  client:
    registerWithEureka: false
    fetchRegistry: false
    region: eu-west-1
management:
  endpoints:
    web:
      exposure:
        include: health, info
    health:
      show-details: never
      probes.enabled: true
```

- **Eureka client** : standalone mode (does not register with other Eureka server)
- **Endpoints actuator** : Exposes `health` and `info` endpoints

## Prerequisites

- **Java 21**
- **Maven**
- **Docker (optional)**

---

## Installation and usage

1. **Clone the repository** :
   ```bash
   git clone https://github.com/Pitchouneee/spring-cloud-eureka-discovery.git
   cd spring-cloud-eureka-discovery
   ```

2. **Build project** :
   ```bash
   mvn clean install
   ```

3. **Start application** :
   ```bash
   mvn spring-boot:run
   ```

4. Access to the Eureka dashboard :  
   Open a browser and navigate to [http://localhost:8761](http://localhost:8761)

---

## Dependencies

- **Spring Boot Starter Actuator** : provides moniotoring and management endpoints
- **Spring Cloud Netflix Eureka Server** : implements the Eureka server
- **Caffeine** : offers high-performance caching capabilities

---

## Contribution

Contributions are welcome ! If you want to report an issue or suggest feature, feel free to open an issue or submit a pull request