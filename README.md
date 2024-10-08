# **Vizinet**
An interactive network protocol simulator to visualize and mimic TCP, UDP, and HTTP protocols.

## **Overview**
**Vizinet** is a web-based network protocol simulator that provides an interactive and visual approach to understanding how network communication works. The application simulates real-world protocols like **TCP**, **UDP**, and **HTTP**, allowing users to observe and interact with packet flow, retransmissions, and different network conditions (such as packet loss and latency). By visualizing these abstract concepts, Vizinet serves as an educational tool for both students and network engineers looking to deepen their understanding of network protocols and their behavior.

## **Features**
- **Protocol Simulation**:
  - **TCP**: Visualize the TCP handshake (SYN, SYN-ACK, ACK), sliding window mechanism, retransmissions, and connection termination.
  - **UDP**: Simulate connectionless data transfer and packet loss without retransmission, demonstrating the differences with TCP.
  - **HTTP**: Explore client-server interactions with HTTP requests and responses, including status codes, headers, and payloads.
  
- **Real-Time Visualizations**:
  - Watch real-time animations of packet flow between clients and servers.
  - View detailed packet information, including sequence numbers, payloads, and protocol-specific details.
  
- **Interactive Topology**:
  - Customize network topologies by adding clients, servers, and routers.
  - Introduce network conditions such as **latency**, **packet loss**, and **network congestion**, and observe how protocols adapt.

- **Live Data**:
  - Leverage **WebSocket** technology to provide real-time updates during simulation, ensuring smooth and instant feedback as users interact with the tool.

- **Simulation History**:
  - Save and load past simulations for reviewing protocol behavior or comparing performance metrics across different scenarios.

## **Technology Stack**
- **Backend**:
  - **Java** (Spring Boot): Handles protocol logic (TCP, UDP, HTTP), session management, and data processing.
  - **PostgreSQL**: Used for storing user profiles, simulation history, and configurations.
  - **Redis**: Provides fast, real-time data management for packet events and session state during live simulations.

- **Frontend**:
  - **React.js**: A modern JavaScript library for building user interfaces, providing a smooth and responsive simulation experience.
  - **D3.js**: Visualizes the network packet flow and protocol details with dynamic, interactive graphs and animations.
  - **WebSockets**: Ensures real-time communication between the backend and frontend, providing instant updates for protocol behavior during simulations.

- **Deployment**:
  - **Docker**: Containers for easy deployment, ensuring consistent environments across development, testing, and production.
  - **Heroku** (or other cloud platforms): Backend and frontend deployment, ensuring WebSocket support for real-time communication.

## **Installation and Setup**
### **Prerequisites**
- **Java** (11+)
- **Node.js** (14+)
- **PostgreSQL**
- **Redis**
- **Docker** (optional but recommended for simplified deployment)

### **Backend Setup**
1. Clone the repository and navigate to the backend directory.
    ```bash
    git clone https://github.com/your-username/vizinet.git
    cd vizinet/backend
    ```
2. Build and run the backend:
    ```bash
    ./mvnw clean install
    ./mvnw spring-boot:run
    ```
3. Ensure PostgreSQL and Redis are running locally or use Docker to start containers.
4. Update the `application.properties` file with your database configuration.

### **Frontend Setup**
1. Navigate to the frontend directory.
    ```bash
    cd vizinet/frontend
    ```
2. Install dependencies and start the development server:
    ```bash
    npm install
    npm start
    ```
### **Running with Docker (optional)**
1. Use Docker Compose to run the entire stack (frontend, backend, PostgreSQL, Redis):
    ```bash
    docker-compose up --build
    ```

## **Usage**
- Open your browser and navigate to `http://localhost:3000`.
- Select a protocol (TCP, UDP, or HTTP) and configure your network topology.
- Start the simulation and observe how packets are sent and received between clients and servers.
- Adjust network conditions and observe how the protocols react to latency, packet loss, or congestion.
- View real-time updates in the packet flow, sequence numbers, retransmissions, and protocol-specific data.

## **Future Improvements**
- Add more protocols (ICMP, FTP).
- Support for more detailed network configurations (custom IP routing, subnetting).
- Advanced performance analytics, including detailed logs of packet RTT, throughput, and error rates.
- Multi-user mode allowing collaborative simulations in real-time.
