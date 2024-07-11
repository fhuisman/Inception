<div align="center">
  <h1>Inception</h1>
  <p>A Dockerized environment with three interconnected containers for hosting a WordPress site.
  This setup uses Nginx as the web server, WordPress with PHP-FPM as the CMS, and MariaDB as the database, all orchestrated with Docker Compose.</p>
</div>

# About the project
This project demonstrates the use of Docker to create a scalable and maintainable environment for hosting a WordPress site. It involves three containers:
- Nginx: Serves as the web server.
- WordPress with PHP-FPM: Content Management System.
- MariaDB: Database server to store WordPress data.

# Getting started

Before you begin, ensure you have the following installed:
- Docker
- Docker Compose

Start by cloning the repository:
```c
git clone https://github.com/fhuisman/Inception
```
Replace the env.example file with a .env file and configure your environment variables as needed.

Go into the inception directory and compile by using make:
```c
make
```
Inception is creating directories in the home folder, you might need to enter your sudo password to do so.

# Usage

To start the containers:
```c
make up 
```

To stop the containers:
```c
make down
```

to remove all containers, images, volumes and networks:
```c
make clean
```
Keep in mind this will also remove the locally stored data in the WordPress and MariaDB volumes.
It might also ask for your sudo password.
