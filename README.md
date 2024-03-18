# DLS Backend

## Contributors

- Morten Bendeke
- Betül Iskender
- Yelong Hartl-He
- Zack Ottesen

## General Use

This repository is the backend for DLS project spring 2024. The repository contains the logic handling user registration and user login. 
This repo is divided into seperate folders with separate responsibilities:
- Controller: Contains setting up the user class, a function to connect to database, and a function to hash passwords when a user logs in.
- Migrations: Contains different snapshot of the database. 
- Models: Contains a model of the user, register and login and setting up the user entity in the database.
- Utility: Contains code for JWT generation and RabbitMQ for consuming updates on the user. 

## Environment Variables

Create a .env in the root folder.

- JWT_SECRET='2b13d563f605b3bb6b5f43ec95a2aaeef1d780049d91d62e0d7c04d70d46de44'
- RABBITMQ_HOST='localhost'
- RABBITMQ_USERNAME='user'
- RABBITMQ_PASSWORD='password'

## How To Run

Make sure the environment variables are set.<br

For Visual Studio, open a terminal and run following each line seperate: 

 - Add-Migration InitialCreate
 - Update-Database
 - Add-Migration MigrationName
 - Update-Database

Make sure to have dotnet installed.
For Jetbrains Rider, open a terminal and run following each line seperate: 

 - dotnet tool install --global dotnet-ef
 - dotnet ef --version
 - dotnet add package Microsoft.EntityFrameworkCore.Design
 - dotnet ef migrations add InitialCreate
 - dotnet ef database update
 - dotnet build

## Dependencies

 - Microsoft.EntityFrameworkCore.Design: Using EntityFramework to set up entities based on the database structure.  
 - Microsoft.EntityFrameworkCore.SqlServer: Using EntityFramework to connect to a SQL server 
 - Microsoft.AspNetCore.Mvc: A framework for building web APIs and web applications using the Model-View-Controller (MVC) pattern.
 - Microsoft.EntityFrameworkCore: EntityFramework Core, an object-relational mapping (ORM) framework that simplifies data access for .NET applications.
 - DotNetEnv : Used to set up a environmental file.
 - BCrypt.net-next: Used for crypting password.
 - System.IdentityModel.Tokens.Jwt: Used to generate tokens for users. 
 - Swashbuckle.AspNetCore: Setting up Swagger / API endpoints
 - RabbitMQ.Client: A .NET client library for RabbitMQ, a message broker that implements the Advanced Message Queuing Protocol (AMQP).

