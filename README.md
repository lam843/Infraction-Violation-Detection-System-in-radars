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
- Web services integration REST, GraphQL, SOAP et GRPC :
- Registration Service Based on Spring data:

![image](https://github.com/lam843/Radar-Violation-Detection-System/assets/78732216/63a47600-8ea6-484c-aa08-0d8db53f6b96)
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


> a. REST :

Tests with `Postman`

<table>
    <tr>
        <td >
            <h5 align="center">All Vehicles</h3>
                <p align="center">
                    <img src="https://github.com/el-moudni-hicham/radar-violation-detection-system/assets/85403056/77beb752-739f-47fd-845f-c666ea4ab362" alt="project example"/>
                </p>
        </td>
    </tr>
    <tr>
        <td >
            <h5 align="center">Find Vehicle By Id</h3>
                <p align="center">
                    <img src="https://github.com/el-moudni-hicham/radar-violation-detection-system/assets/85403056/4b2cf16c-1340-4404-8cec-1bcdc51f524c" alt="project example"/>
                </p>
        </td>
    </tr>
</table>

<table>
    <tr>
        <td >
            <h5 align="center">Delete Vehicle</h3>
                <p align="center">
                    <img src="https://github.com/el-moudni-hicham/radar-violation-detection-system/assets/85403056/7a2c7083-7539-4dcd-b506-3556fec50c3a" alt="project example"/>
                </p>
        </td>
    </tr>
    <tr>
        <td >
            <h5 align="center">Update Vehicle</h3>
                <p align="center">
                    <img src="https://github.com/el-moudni-hicham/radar-violation-detection-system/assets/85403056/270691bf-1f79-446c-9359-20fec739881c" alt="project example"/>
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
                         src="https://github.com/el-moudni-hicham/radar-violation-detection-system/assets/85403056/e29db325-f14f-4d6a-9916-0ee1d1760da0"/>
                </p>
        </td>
    </tr>
    <tr>
        <td>
            <h5 align="center">Find Vehicle By Id with specific attributs</h3>
                <p align="center">
                    <img alt="project example"
                         src="https://github.com/el-moudni-hicham/radar-violation-detection-system/assets/85403056/15f188ac-d384-455d-a8ed-91363143f97f"/>
                </p>
        </td>
    </tr>
</table>

> c. SOAP :

Tests with `SoapUI`
<table>
    <tr>
        <td >
            <h5 align="center">All Owners </h3>
                <p align="center">
                    <img src="https://github.com/el-moudni-hicham/radar-violation-detection-system/assets/85403056/7a01b2b9-3807-43e1-884d-8c0cbfcbb994" alt="project example"/>
                </p>
        </td>
    </tr>
    <tr>
        <td >
            <h5 align="center">Find Owner By Id</h3>
                <p align="center">
                    <img src="https://github.com/el-moudni-hicham/radar-violation-detection-system/assets/85403056/52bc6d85-1dc1-4f00-b9da-701d500a8b4a" alt="project example"/>
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
                         src="https://github.com/el-moudni-hicham/radar-violation-detection-system/assets/85403056/abc8437c-d043-4821-b684-0a27917cb13c"/>
                </p>
        </td>
    </tr>
    <tr>
        <td>
            <h5 align="center">Find Owner By Id</h3>
                <p align="center">
                    <img alt="project example"
                         src="https://github.com/el-moudni-hicham/radar-violation-detection-system/assets/85403056/7b33bad2-3ac7-415d-ab60-33d3ae23b08e"/>
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
                     src="https://github.com/el-moudni-hicham/radar-violation-detection-system/assets/85403056/0068cd62-3044-47ad-b1ac-a03c34713801"/>
            </p>
        </td>
    </tr>

</table>

# Frontend with Angular
