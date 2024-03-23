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

## Usage

1. **Installation**:
   - Clone the repository.
   - Install dependencies using `pip` or `requirements.txt`.

2. **Configuration**:
   - Set up Kubernetes cluster.
   - Configure RabbitMQ, MongoDB, and MySQL connections in the microservice.

3. **Deployment**:
   - Deploy microservices using Kubernetes manifests.
   - Scale and manage microservices using Kubernetes commands.

4. **Usage**:
   - Send audio files to be converted using the RESTful API.
   - Monitor conversions and retrieve converted MP3 files using the API.

## Contributing

Contributions to the MP3 Converter Microservice are welcome! 

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- [Kubernetes Documentation](https://kubernetes.io/docs/)
- [RabbitMQ Tutorials](https://www.rabbitmq.com/getstarted.html)
- [MongoDB Documentation](https://docs.mongodb.com/)
- [MySQL Documentation](https://dev.mysql.com/doc/)

