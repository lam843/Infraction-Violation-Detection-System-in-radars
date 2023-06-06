# Radar Violation Detection System (SD project)


This application is a combination of a web-based frontend and backend. The frontend is developed using Angular with Bootstrap for a user-friendly interface, while the backend is built using Spring Boot. Its main purpose is to detect and track radar violations in real-time, ensuring efficient traffic management.

The system offers various functionalities beyond the standard data querying and modification operations. It allows users to submit speeding violations, which are recorded as offense records. Additionally, vehicle owners can easily access and view their own violation history, providing them with convenient access to their offense records.


# Table of Contents
- [Getting Started](#getting-started)
    - [Prerequisites](#prerequisites)
- [Technologies Used](#technologies-used)
- [Technical Architecture](#technical-architecture)
- [Class Diagram](#class-diagram)
- [Backend Services](#backend-services)
    - [Registration Service](#registration-service)
    - [Radar Service](#radar-service)
    - [Infraction Service](#infraction-service)
    - [Eureka Discovery Service](#eureka-discovery-service)
    - [Gateway Service](#gateway-service)
    - [Road Radar](#road-radar)
- [Frontend with Angular](#frontend-with-angular)
- [License](#license)


## Getting Started
### Prerequisites
Before running this application, you need to have the following software installed on your system :

```java
- Java Development Kit (JDK) version 11 or later
- Node.js version 14 or later
- Angular CLI version 13 or later
```

## Technologies Used
The following technologies and frameworks are used in this application:

- Spring Boot
- Spring Cloud
- Eureka Descovery
- Angular
- Bootstrap
- MySQL

## Functionalities

The application allows performing the following operations:
- Submit a speeding violation.
- View violations of a vehicle owner.
- Modify and view radar data.
- Modify and view vehicle and owner data.
- Modify and view infraction data.

## Technical Architecture



## Class Diagram 



## Backend Services

The backend contains 5 services :

### Regestration Service 

```
Registration microservice manages vehicles owned by owners. Each vehicle belongs to a single owner.
An owner is defined by their ID, name, date of birth, email.
A vehicle is defined by its ID, regestration number, brand, fiscal power, and model
```
- Service Structure
<pre>

├───src
│   ├───main
│   │   ├───java
│   │   │   └───ma
│   │   │       └───example
│   │   │           └───registrationservice
│   │   │               │   RegistrationServiceApplication.java
│   │   │               │
│   │   │               ├───entites
│   │   │               │       Owner.java
│   │   │               │       OwnerRequest.java
│   │   │               │       Vehicle.java
│   │   │               │
│   │   │               ├───repositories
│   │   │               │       OwnerRepository.java
│   │   │               │       VehicleRepository.java
│   │   │               │
│   │   │               └───web
│   │   │                   ├───graphql
│   │   │                   │       OwnerGraphqlController.java
│   │   │                   │       VehicleGraphqlController.java
│   │   │                   │
│   │   │                   ├───grpc
│   │   │                   │   │   GrpcConfig.java
│   │   │                   │   │   OwnerGrpcService.java
│   │   │                   │   │
│   │   │                   │   └───stub
│   │   │                   │           OwnerGrpcServiceGrpc.java
│   │   │                   │           OwnerService.java
│   │   │                   │
│   │   │                   ├───rest
│   │   │                   │       OwnerRestController.java
│   │   │                   │       VehicleRestController.java
│   │   │                   │
│   │   │                   └───soap
│   │   │                           CXFSoapWebServiceConfig.java
│   │   │                           OwnerSoapController.java
│   │   │                           OwnerSoapService.java
│   │   │
│   │   └───resources
│   │       │   application.properties
│   │       │   owner-service.proto
│   │       │   xsd-schema.xsd
│   │       │
│   │       ├───graphql
│   │       │       schema.graphqls
│   │       │
│   │       ├───static
│   │       └───templates

</pre>

- Registration Service Based on Spring data:

<table>
    <tr>
        <td >
            <h5 align="center">All Vehicles</h3>
                <p align="center">
                    <img src="https://github.com/lam843/Radar-Violation-Detection-System/assets/78732216/63a47600-8ea6-484c-aa08-0d8db53f6b96" alt="project example"/>
                </p>
        </td>
    </tr>
    <tr>
        <td >
            <h5 align="center">Find Vehicle By Id</h3>
                <p align="center">
                    <img src="https://github.com/lam843/Radar-Violation-Detection-System/assets/78732216/15ae2391-cec2-4c90-9840-04f698751df9" alt="project example"/>
                </p>
        </td>
    </tr>
</table>

- Web services integration REST, GraphQL, SOAP et GRPC :
> a. REST :

Tests with `Postman`

<table>
    <tr>
        <td >
            <h5 align="center">All Vehicles</h3>
                <p align="center">
                    <img src="https://github.com/lam843/Radar-Violation-Detection-System/assets/78732216/aed50fa0-af3c-4507-975b-544e2e1122b4" alt="project example"/>
                </p>
        </td>
    </tr>
    <tr>
        <td >
            <h5 align="center">Find Vehicle By Id</h3>
                <p align="center">
                    <img src="https://github.com/lam843/Radar-Violation-Detection-System/assets/78732216/a5ef4a02-9985-4a21-b9cf-bf358ee63f43" alt="project example"/>
                </p>
        </td>
    </tr>
    <tr>
        <td >
            <h5 align="center">Find Vehicle Owner</h3>
                <p align="center">
                    <img src="https://github.com/lam843/Radar-Violation-Detection-System/assets/78732216/86703b0e-788b-4000-9816-adca387c39ab" alt="project example"/>
                </p>
        </td>
    </tr>

</table>

<table>
    <tr>
        <td >
            <h5 align="center">Delete Vehicle</h3>
                <p align="center">
                    <img src="https://github.com/lam843/Radar-Violation-Detection-System/assets/78732216/edf989b2-73dc-4ffe-8765-3568d755efc5" alt="project example"/>
                </p>
        </td>
    </tr>
    <tr>
        <td >
            <h5 align="center">Update Vehicle</h3>
                <p align="center">
                    <img src="https://github.com/lam843/Radar-Violation-Detection-System/assets/78732216/3b704147-a0f9-420f-a31f-4798f4b6f56f" alt="project example"/>
                </p>
        </td>
    </tr>
</table>


> b. GraphQL :
<table>
    <tr>
        <td>
            <h5 align="center">All Vehicles with specific attributs </h3>
                <p align="center">
                    <img alt="project example"
                         src="https://github.com/lam843/Radar-Violation-Detection-System/assets/78732216/9f10a680-0510-4ecc-97a3-4b14e6ede21e"/>
                </p>
        </td>
    </tr>
    <tr>
        <td>
            <h5 align="center">Find Vehicle By Id with specific attributs</h3>
                <p align="center">
                    <img alt="project example"
                         src="https://github.com/lam843/Radar-Violation-Detection-System/assets/78732216/6d4d5d5f-f73d-4a23-ac66-dcb841779d80"/>
                </p>
        </td>
    </tr>
    <tr>
        <td>
            <h5 align="center">All owners</h3>
                <p align="center">
                    <img alt="project example"
                         src="https://github.com/lam843/Radar-Violation-Detection-System/assets/78732216/d342d008-e19b-46bc-a4fc-dac60eea1394"/>
                </p>
        </td>
    </tr>

</table>

> c. SOAP :

Tests with `SoapUI`
<table>
    <tr>
        <td >
            <h5 align="center"Owners By Id</h3>
                <p align="center">
                    <img src="https://github.com/lam843/Radar-Violation-Detection-System/assets/78732216/e8045083-637a-4491-8b52-ad2cbc8ed36a" alt="project example"/>
                </p>
        </td>
    </tr>
    <tr>
        <td >
            <h5 align="center"> Specific Owner information </h3>
                <p align="center">
                    <img src="https://github.com/lam843/Radar-Violation-Detection-System/assets/78732216/a29174a6-e5fd-4c80-b897-2919d12e525e" alt="project example"/>
                </p>
        </td>
    </tr>
</table>

> d. GRPC :

Tests with `BloomRPC`
<table>
    <tr>
        <td>
            <h5 align="center">All Owners </h3>
                <p align="center">
                    <img alt="project example"
                         src="https://github.com/lam843/Radar-Violation-Detection-System/assets/78732216/91ffba1e-ed2f-456c-a898-278b927d4766"/>
                </p>
        </td>
    </tr>
    <tr>
        <td>
            <h5 align="center">Find Owner By Id</h3>
                <p align="center">
                    <img alt="project example"
                         src="https://github.com/lam843/Radar-Violation-Detection-System/assets/78732216/a034e5a4-cc11-4fc8-b3f7-10c5abdff15e"/>
                </p>
        </td>
    </tr>
</table>



####

### Radar Service 

```
Radar microservice responsible for managing radars handles radar entities defined
by their ID, maximum speed limit, and coordinates (longitude and latitude)
```
- Service Structure
<pre>
├───src
│   ├───main
│   │   ├───java
│   │   │   └───ma
│   │   │       └───example
│   │   │           └───radarservice
│   │   │               │   RadarServiceApplication.java
│   │   │               │
│   │   │               ├───entites
│   │   │               │       Radar.java
│   │   │               │
│   │   │               ├───feign
│   │   │               │       InfractionRestClient.java
│   │   │               │
│   │   │               ├───models
│   │   │               │       Infraction.java
│   │   │               │       NewData.java
│   │   │               │
│   │   │               ├───repositories
│   │   │               │       RadarRepository.java
│   │   │               │
│   │   │               └───web
│   │   │                       RadarRestController.java
│   │   │
│   │   └───resources
│   │       │   application.properties
│   │       │   radar-service.proto
│   │       │
│   │       ├───static
│   │       └───templates
</pre>

### Infraction Service 

```
Infraction microservice responsible for managing violations handles each violation, which is defined
by its ID, date, the radar number that detected the offense, the vehicle regestration number,
the vehicle's speed, the radar's maximum speed limit, and the fine amount.
```
- Service Structure
<pre>
├───src
│   ├───main
│   │   ├───java
│   │   │   └───ma
│   │   │       └───example
│   │   │           └───infractionservice
│   │   │               │   InfractionServiceApplication.java
│   │   │               │
│   │   │               ├───entites
│   │   │               │       Infraction.java
│   │   │               │
│   │   │               ├───feign
│   │   │               │       RadarRestClient.java
│   │   │               │       VehicleRestClient.java
│   │   │               │
│   │   │               ├───models
│   │   │               │       NewData.java
│   │   │               │       Owner.java
│   │   │               │       Radar.java
│   │   │               │       Vehicle.java
│   │   │               │
│   │   │               ├───repositories
│   │   │               │       InfractionRepository.java
│   │   │               │
│   │   │               └───web
│   │   │                       InfractionRestController.java
│   │   │
│   │   └───resources
│   │       │   application.properties
│   │       │
│   │       ├───static
│   │       └───templates
</pre>

### Eureka Discovery Service
```
server-side component in the Netflix OSS stack that allows services to register
and discover each other in a microservices architecture.
```
- Service Structure
<pre>
├───src
│   ├───main
│   │   ├───java
│   │   │   └───ma
│   │   │       └───example
│   │   │           └───eurekadiscovery
│   │   │                   EurekaDiscoveryApplication.java
│   │   │
│   │   └───resources
│   │           application.properties
│   │
│   └───test
│       └───java
│           └───ma
│               └───example
│                   └───eurekadiscovery
│                           EurekaDiscoveryApplicationTests.java
│
</pre>

### Gateway Service
```
Spring Cloud Gateway It provides a centralized entry point for routing and filtering requests
to microservices in a distributed system, enabling dynamic and scalable routing based on various criteria.
```
- Service Structure
<pre>
├───src
│   ├───main
│   │   ├───java
│   │   │   └───ma
│   │   │       └───example
│   │   │           └───gateway
│   │   │                   GatewayApplication.java
│   │   │
│   │   └───resources
│   │           application.properties
│   │           application.yml
</pre>

### Road Radar
```
A Java application that simulates a radar system generating random speeding violations
and sending them to the Radar-Service.
```

- Service Structure
<pre>
├───src
│   ├───main
│   │   ├───java
│   │   │   └───ma
│   │   │       └───example
│   │   │           └───radarroad
│   │   │               │   RadarDetectionService.java
│   │   │               │   RadarRoadApplication.java
│   │   │               │
│   │   │               └───models
│   │   │                       NewData.java
│   │   │                       Radar.java
│   │   │                       Vehicle.java
│   │   │
│   │   └───resources
│   │       │   application.properties
│   │       │
│   │       ├───static
│   │       └───templates
</pre>

* Test

<table>
    <tr>
        <td>
            <p align="center">
                <img alt="project example"
                     src=""/>
            </p>
        </td>
    </tr>

</table>

# Frontend with Angular
