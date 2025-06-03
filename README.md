# Peer Vault - Service Discovery

## 🚀 Overview
The **Service Discovery** module, powered by Eureka Server, is a central component of the Peer Vault microservices architecture. It enables microservices to register themselves and discover other services dynamically, facilitating flexible and scalable communication within the ecosystem.

---

## ✨ Features
* **Centralized service registration** for all microservices
* **Dynamic service discovery** for inter-service communication
* Built-in **client-side load balancing** integration
* Provides a **dashboard** for monitoring registered services
* Seamlessly integrates with the Spring Cloud ecosystem

---

## 🛠 Tech Stack
* Spring Boot
* Spring Cloud Netflix Eureka Server
* Docker & Docker Compose (optional for containerized deployment)

---

## 🏗 Installation & Setup

### Prerequisites
* Java 17 or higher
* Maven
* Git
* Docker and Docker Compose (optional)

### Backend Setup

1.  **Clone the Service Discovery repository:**
    ```bash
    git clone [https://github.com/Peer-Vault/Service-Discovery.git](https://github.com/Peer-Vault/Service-Discovery.git)
    cd Service-Discovery
    ```

2.  **Configure the Service Discovery `application.yml`** (located in the `src/main/resources` folder) to connect to your Config Server. An example `application.yml` would look like this:
    ```yaml
    spring:
      application:
        name: servicediscovery
      config:
        import: optional:configserver:http://localhost:8071/

    server:
      port: 8761 # Default Eureka Server port
    ```

3.  **Run the Service Discovery Server:**

    **Option 1: Run Locally**
    ```bash
    mvn spring-boot:run
    ```

    **Option 2: Run with Docker**
    If you're using Docker, ensure your `docker-compose.yml` file includes the Service Discovery service, then run:
    ```bash
    docker-compose up service-discovery
    ```

---

## 🎯 Usage
* Start the **Config Server** and then the **Service Discovery Server** before starting any other microservices.
* Microservices will register themselves with this Eureka Server upon startup.
* You can monitor the registered services by accessing the Eureka dashboard in your browser:
    ```bash
    http://localhost:8761/
    ```

---

## 🤝 Contributing
Contributions and suggestions are welcome! Feel free to open issues or submit pull requests to improve the project.

---

## 👨‍💻 Author
Developed and maintained by the Peer Vault team.

---

🌟 Star this repo if you find it helpful! 🌟
