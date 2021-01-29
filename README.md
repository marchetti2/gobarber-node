<h2>About</h2>

This is the third module of GoStack(old journey) from [RocketSeat](https://rocketseat.com.br/). 
This repository is **only the backend** of the application, the web and mobile versions are part of the next modules.

> **GoBarber** is an application designed for service management between barbers and customers.

With Gobarber it is possible to register and make an appointment/service with your barber and/or become a provider of these services.

<h2>Summary</h2>

- [Technologies](#technologies)
- [Getting started](#started)
  - [Download](#download)
  - [Environment](#environment)
    - [Databases](#databases)
    - [Environment variables](#variables)
  - [Running the API](#running)
    - [Tolls](#tools)
- [License](#license)

<h2 id="technologies">Technologies</h2>

- [Node.js](https://nodejs.org/en/)
- [Express](http://expressjs.com/)
- [PostgreSQL](https://hub.docker.com/_/postgres)
- [MongoDB](https://hub.docker.com/_/mongo)
- [Redis](https://hub.docker.com/_/redis)
- [Sequelize](https://sequelize.org/)
- [Mailtrap.io](https://mailtrap.io/)

<h6>Tools</h6>

- [Nodemon](https://nodemon.io/)
- [Sucrase](https://github.com/alangpierce/sucrase)
- [Eslint](https://eslint.org/)
- [Prettier](https://prettier.io/)
- [EditorConfig](https://editorconfig.org/)

<h6>REST API Client</h6>

- [Insomnia](https://insomnia.rest/)
- [PostBird](https://www.electronjs.org/apps/postbird)

<h2 id="started">Getting started</h2>

Before downloading and running the project, you must have **Node.js** already installed and then install the following tools: 

- [Node.js](https://nodejs.org/en/)

> Unfortunately, sequelize migrations only work until Node version 10.13.0. I recommend using the node version manager **[nvm](https://github.com/nvm-sh/nvm)** to install this version.

- [Git](https://git-scm.com/)
- [Yarn](https://yarnpkg.com/)
- [Docker](https://www.docker.com/get-started)

<h4 id="download">Download</h4>

Open the terminal and execute the following commands: 

```bash
  # Clone the project
  $ git clone https://github.com/marchetti2/GoBarberNode.git

  # Access the folder
  $ cd GoBarberNode

  # Install the dependencies
  $ yarn
```
<h4 id="environment">Environment</h4>

<h6 id="databases">Databases</h6>

Using the **docker**, start an instance of the databases below.

```bash
  # PostgreSQL 
  $ docker run --name postgres -e POSTGRES_PASSWORD=docker -p 5432:5432 -d postgres

  # MongoDB
  $ docker run --name mongodb -p 27017:27017 -d -t mongo

  # Redis
  $ docker run --name redis -p 6379:6379 -d -t redis:alpine
```
To find out if the databases are running, run the following command:
```bash
$ docker ps
```
If not, run:

```bash
$ docker start postgres mongodb redis
```
<h6 id="variables">Environment variables</h6>

From the `.env.example` file at the root of the project, create another file called` .env` using the same structure and completing the missing variables.

<h2 id="running">Running the API</h2>

First, verify that the databases are running. From the API directory, run the following commands:

```bash
  # Create tables in PostgreSQL
  $ yarn sequelize db:migrate
  $ yarn sequelize db:seed:all

  # Run the server
  $ yarn dev
  $ yarn queue
```
<h6 id="tools">Tools</h6>

- To view the tables created in the postgres database, use the [PostgreSQL GUI client](https://www.electronjs.org/apps/postbird).

- To test the routes, you can use [Insomnia](https://insomnia.rest/). The workspace used in this API is available, just click the button below. 
<p align="center">
<a href="https://insomnia.rest/run/?label=goBarber&uri=https%3A%2F%2Fgist.githubusercontent.com%2Fmarchetti2%2F7a60dfab137a9e7c474e51f9a7f4a9ae%2Fraw%2F89d6dee8d369f66165407dbfc201d945e5785f40%2FgoBarber.json" target="_blank"><img src="https://insomnia.rest/images/run.svg" alt="Run in Insomnia"></a>
</p>

<h2 id="license">License</h2>

This is a [RocketSeat](https://rocketseat.com.br) GoStack course project(old journey).
