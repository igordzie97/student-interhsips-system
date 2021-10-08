# System supporting student internships

## Table of Consents
1. [Description](#opis)
2. [Technologies and system architecture](#technologie-i-architektura-systemu)
  - [Backend](#backend)
  - [Database](#baza-danych)
  - [Frontend](#frontend)
3. [Documentation](#dokumentacja)

## Description
The engineer thesis purpose was to design and implement system which will support process of student internships. The main goal is to simplifie and digitize whole process.

System as Web Application, allows
- registration of the students
- adding companies that organise internships 
- adding documents
- approving documents by companies and universities supervisors
- communicating with integrated communication system

## Technologies and system architecture
- **Java 11 + Spring Boot** - Backend
- **Vue.js 3.0** - Frontend
- **MySQL** - Relational Database Management System
- **Hibernate** - Object-Relational Mapping framework
- **Swagger** – Automated documentation for describing RESTful APIs (expressed using JSON)

<img width="900" alt="Screen Shot 2021-10-09 at 00 55 35 AM" src="https://user-images.githubusercontent.com/34041060/136632722-f6ed5408-2462-434d-bbaf-05d9d6d1cd29.png">

## Backend
Api oparte na stylu architektonicznym **REST**. Jako formę autoryzacji oraz autentyfikacji został wybrany mechanizm **JWT**.

### Najważniejsze zależności z pliku pom.xml:
- **spring-boot-starter-web** - narzędzia nezbędne do tworzenia aplikacji webowej.
- **spring-boot-starter-data-jpa** - warstwa abstrakcji nad bazą danych.
- **mysql-connector-java** - sterownik JDBC dla MySQL.
- **spring-boot-starter-security** - zbiór narzędzi do zabezpieczenia aplikacji (między innymi mechanizm JWT).

### Swagger
Dokumentacja API, która pozwala on na wizualizowanie zasobów serwera, które dzielone są na kontrolery.
- znaczne przyspieszenie pracy nad serwerem
- ułatwienie testów
- zaoszczędzenie czasu na korzystaniu z zewnętrznych aplikacji (Postman / Insomnia)

Zależności z pliku pom.xml:

<img width="300" alt="Screen Shot 2021-08-23 at 00 56 12 AM" src="https://user-images.githubusercontent.com/34041060/130372643-b7ebaec0-5fd8-45b7-8904-d0554adade24.png">

Skonfigurowany w klasie SwaggerConfig, w wersji 3.0. Zawiera dodatkową konfigurację, gdzie przy każdym request dołączany jest wskazany wcześniej token JWT:

<img width="650" alt="Screen Shot 2021-08-23 at 00 46 53 AM" src="https://user-images.githubusercontent.com/34041060/130372433-9fb81c08-9212-4f49-8ca8-fec2d111e299.png">

### Project Lombok
Biblioteka Javy, która w znaczącym stopniu ułatwia definiowanie klas. Znacząco skraca kod poprzez zastąpienie getterów, setterów, czy konstruktorów za pomocą adnotacji.

Zależności z pliku pom.xml:

<img width="300" alt="Screen Shot 2021-08-23 at 00 55 47 AM" src="https://user-images.githubusercontent.com/34041060/130372630-4725e7a6-ed2e-406e-9798-117f4c284660.png">

### Adres
-  http://localhost:9090
-  **Swagger:** http://localhost:9090/swagger-ui/index.html#/

## Baza danych

Konfiguracja bazy danych z pliku application.properties: 

<img width="800" alt="Screen Shot 2021-08-23 at 00 14 31 AM" src="https://user-images.githubusercontent.com/34041060/130371689-40e3d893-2c16-447d-a9f3-087011103e9c.png">

- **Nazwa bazy danych**: db_studentIntershipSupport
- **Nazwa użytkownika:** springuser
- **Hasło użytkownika:** ThePassword

## Frontend
Do komunikacji z serwerem została wykorzystana biblioteka **axios**, będąca klientem HTTP, który jednoznacznie określa sposób wymiany informacji oraz współpracy.

W aspekcie wizualnym została wykorzystana bilbioteka komponentów dla Vue.js w wersji 3.0, Element Plus: 
- https://element-plus.org/#/en-US

Jako menadżer pakietów została wykorzystana oficjalna propozycja od twórców Node.js - Npm. 

### Uruchomienie
`npm install` - ściągnięcie wszystkich potrzebnych paczek (node_modules), które są zdefiniowane w package.json.

`npm run serve` - uruchomienie aplikacji, które zwraca pod jakim adresem można otworzyć lokalny projekt.

### Adres
- https://localhost:8080

## Documentation
- [Koncepcyjna](https://github.com/igordzie97/student-interhsips-system/blob/main/documentation/dok-koncepcyjna.pdf)
- [Specyfikacyjna](https://github.com/igordzie97/student-interhsips-system/blob/main/documentation/dok-specyfikacyjna.pdf)
- [Procesowa](https://github.com/igordzie97/student-interhsips-system/blob/main/documentation/dok-procesowa.pdf)
- [Deweloperska](https://github.com/igordzie97/student-interhsips-system/blob/main/documentation/dok-deweloperska.pdf)
- [Użytkownika](https://github.com/igordzie97/student-interhsips-system/blob/main/documentation/dok-użytkownika.pdf)

## Autorzy:
- Igor Dzierwa
- Adrian Nędza
- Konrad Makuch
