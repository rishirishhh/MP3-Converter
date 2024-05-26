# MP3 Converter Microservice

## Overview

The MP3 Converter Microservice is a distributed system designed to convert audio files to the MP3 format. It utilizes microservice architecture principles to achieve scalability, maintainability, and fault tolerance. This microservice is built using Python and leverages Kubernetes for container orchestration, RabbitMQ for asynchronous message queuing, MongoDB for NoSQL data storage, and MySQL for relational data storage.

## Features

- Converts audio files to the MP3 format
- Scalable and fault-tolerant architecture
- Asynchronous processing using RabbitMQ
- Data storage using MongoDB and MySQL
- RESTful API for interaction with the microservice

## Architecture

The MP3 Converter Microservice follows a microservice architecture, which consists of the following components:

- **Converter Service**: Converts audio files to the MP3 format.
- **Queue Service**: Manages message queuing using RabbitMQ for asynchronous processing.
- **Database Service**: Stores data in both MongoDB (NoSQL) and MySQL (relational) databases.
- **API Gateway**: Provides a RESTful API for interacting with the microservice.

![Screenshot from 2024-03-24 03-08-08](https://github.com/rishirishhh/MP3-Converter/assets/148757583/93d60ea7-bb48-4fde-bc66-2e7255873cb3)

## Technologies Used

- **Python**: Programming language used for implementing the microservice.
- **Kubernetes**: Container orchestration platform for managing and scaling containerized applications.
- **RabbitMQ**: Message broker for asynchronous communication between microservices.
- **MongoDB**: NoSQL database for storing unstructured data.
- **MySQL**: Relational database for storing structured data.

### Getting Started
You'll need to do the following pre-requisites before you can use Docker Stacks to perform Kubernetes deployments using YAML files.

### Pre-requisites:

- Install kubectl (https://kubernetes.io/docs/tasks/tools/install-kubectl/)
- Enable Kubernetes (From Docker Desktop)
Turn on Experimental Features (From Docker Desktop)
You can quickly tackle the last two pre-requisites by configuring the Docker preferences pane—which can be found from the menu in the Docker Desktop system tray.
- Make sure Kubernetes enable Ingress.

### How to run

Before run in Kubernetes, You should be change something to make sure while running is correct.
- email, email password to use stmp.
- connection mysql
- connection mongodb

```bash
kubectl apply -f auth/manifests
kubectl apply -f rabbitmq/manifests
kubectl apply -f converter/manifests
kubectl apply -f notification/manifests
kubbectl apply -f gateway/manifests
```

Please configuration into `/etc/hosts` file like this

![hosts](./images/hosts.png)

- Get token by email and password.

```bash
curl -X POST http://mp3converter.com/login -u email:password
```

- Get token using for APIs later.

- Install `youtube-dl` to download video in youtube if you like.

```bash
youtube-dl https://youtu.be/eZJhYgPE3Eg test.mkv
```

- Upload video API

```bash
curl -X POST -F 'file=@./test.mkv' -H 'Authorization: Bearer your_token_here' http://mp3converter.com/upload
```

- Please install [k9s](https://k9scli.io/) to monitoring kubernetes.

```bash
k9s
```
![k9s](./images/k9s.png)

- Check you email and try api get mp3 file.

```bash
curl --output something.mp3 -X GET 'http://mp3converter.com/download?fid=6370a832268bc743b21c729f' \
--header 'Authorization: Bearer your_token_here'

```

#### Happy coding :))
