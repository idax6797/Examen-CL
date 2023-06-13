# CL Eksamen 2023e
## Zay eCommerce

This is a my assignment for the demo project for Containerization & Linux elective at [UCL University College](https://ucl.dk)

The frontend is based on the following template:

* https://github.com/mosaadaldeen/zay-shop

### Frontend

There is a specific README.md file in the frontend project

### Backend

There is a specific README.md file in the backend project

---

## Get started with Docker
1. Open docker desktop on you computer
2. Open the project via the terminal

### Containerize Frontend
In order to containerize the frontend you need to navigate to the frontend folder:
```
cd frontend 
```
and here you can build the image for the front using the command: 

```
docker build -t frontend . 
```

And when you need to run the image in a container you can use the command: 

```
docker run -d -p 8000:5173 frontend
```
This will display the frontend on you localhost. Url: http://localhost:8000/


### Containerize Backend
In order to containerize the backend you then need to navigate to the backend folder

```
cd backend 
```

 and from here you can build the image via this command: 

```
docker build -t backend . 
```
And when you need to run the image in a container you can use the command: 

```
docker run -d -p 3000:3000 backend
```

This will display the backend on you localhost. Url: http://localhost:3000/

### Creating and Running a Container Environment
I order to run the different services specified in the Docker Compose file you need to navigate to the root of the project where the compose file is located.
> **_NOTE:_**  Only use the following command if you are inside the backend or the frontend folder.
```
cd .. 
``` 
Here you can run the following command to start the application: 
```
docker-compose up -d
```
You can now access the services via the same url's as before.

### Test the stack
In order to test the swarm cluster you need to initialize Docker swarm via the command: 

```
docker swarm init
```

After the initialization you can deploy the stack via the command: 

```
docker stack deploy -c test-stack.yml test
```
> **_NOTE:_**  The name *test* can be anything.

The stack is now created and it can be seen via the command: 

```
docker stack ls
```

And the services can be seen via the command: 

```
docker service ls
```

And the individual services in the stack can be seen via the command: 

```
docker stack ps test
```
