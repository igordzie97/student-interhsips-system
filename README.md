# System wspomagający obsługę praktyk studenckich
Celem pracy inżynierskiej było zaprojektowanie i implementacja systemu wspomagającego obsługę procedury zaliczenia praktyk przez studentów. 
Założeniem systemu jest maksymalne uproszczenie procesu i jego cyfryzacja. 

System, jako aplikacja webowa, umożliwia między innymi: 
- rejestrację studentów
- dodawanie firm organizujących praktykę
- dodawanie dokumentów
- zatwierdzanie dokumentów przez opiekunów ze strony firmy i uczelni. 
- zintegrowany system komunikacji umożliwia szybki kontakt opiekuna praktyk ze studentem

# Technologie i architektura systemu
## Stos technologiczny:
- **Java 11 + Spring Boot** - backend
- **Vue.js 3.0** - frontend
- **MySQL** - relacyjny system do zarządzania bazą danych
- **Hibernate** - framework do mapowania obiektowo-relacyjnego (ORM)
- **Swagger** – automatyczna dokumentacja metod RestAPI

<img width="600" alt="Screen Shot 2021-08-23 at 00 11 15 AM" src="https://user-images.githubusercontent.com/34041060/130371599-3721aee0-691e-450d-9d4a-f8d4db3220aa.png">

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

## Baza danych

### Konfiguracja bazy danych z pliku application.properties: 

<img width="800" alt="Screen Shot 2021-08-23 at 00 14 31 AM" src="https://user-images.githubusercontent.com/34041060/130371689-40e3d893-2c16-447d-a9f3-087011103e9c.png">

- **Nazwa bazy danych**: db_studentIntershipSupport
- **Nazwa użytkownika:** springuser
- **Hasło użytkownika:** ThePassword

## Frontend
Do komunikacji z serwerem została wykorzystana biblioteka **axios**, będąca klientem HTTP, który jednoznacznie określa sposób wymiany informacji oraz współpracy.

W aspekcie wizualnym została wykorzystana bilbioteka komponentów dla Vue.js w wersji 3.0, Element Plus: https://element-plus.org/#/en-US

Jako menadżer pakietów została wykorzystana oficjalna propozycja od twórców Node.js - Npm. 
