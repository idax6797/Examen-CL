# CL Eksamen 2023e

This is my examen project in the Containerization & Linux elective at [UCL University College](https://ucl.dk)

The project is based on the following templates:

* https://github.com/mosaadaldeen/zay-shop
* https://github.com/ucldk/cl23e-exam-project

### Frontend

There is a specific README.md file in the frontend project

### Backend

There is a specific README.md file in the backend project

---

## Get started with Docker
1. Open docker desktop on you computer
2. Open the project via the terminal

### Containerize the frontend
In order to containerize the frontend you need to navigate to the frontend folder:
```
cd frontend 
```
Here you can build the image for the frontend using the command: 

```
docker build -t frontend . 
```

When you need to run the image in a container you can use the command: 

```
docker run -d -p 8000:5173 frontend
```
This will display the frontend on you localhost. Url: http://localhost:8000/


### Containerize the backend
In order to containerize the backend you need to navigate to the backend folder

```
cd backend 
```

From here you can build the image via the following command: 

```
docker build -t backend . 
```
When you need to run the image in a container you can use the command: 

```
docker run -d -p 3000:3000 backend
```

This will display the backend on you localhost. Url: http://localhost:3000/

### Creating and running the container environment
I order to run the different services specified in the Docker Compose file you need to navigate to the root of the project, where the compose file is located.
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
> **_NOTE:_**  The name *test* can be changed as desired. It is just the name of the stack.

```
docker stack deploy -c test-stack.yml test
```

The stack is now created and it can be seen via the command: 

```
docker stack ls
```

The services can be seen via the command: 

```
docker service ls
```

The individual services in the stack can be seen via the command: 

```
docker stack ps test
```
