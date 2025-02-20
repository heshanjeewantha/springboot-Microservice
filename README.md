<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Spring Boot Microservices Project</title>
</head>
<body>
    <h1>Spring Boot Microservices Project</h1>
    <p>This project is a collection of microservices built using Spring Boot. The microservices include:</p>
    <ul>
        <li><strong>Product Service</strong>: Manages product information.</li>
        <li><strong>Inventory Service</strong>: Tracks inventory levels for products.</li>
        <li><strong>Order Service</strong>: Handles order creation and management.</li>
    </ul>

    <h2>Table of Contents</h2>
    <ul>
        <li><a href="#overview">Overview</a></li>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#setup">Setup</a></li>
        <li><a href="#running-the-services">Running the Services</a></li>
        <li><a href="#api-endpoints">API Endpoints</a></li>
        <li><a href="#monitoring">Monitoring with Grafana and Prometheus</a></li>
        <li><a href="#authentication">Authentication with Keycloak</a></li>
        <li><a href="#contributing">Contributing</a></li>
        <li><a href="#license">License</a></li>
    </ul>

    <h2 id="overview">Overview</h2>
    <p>This project demonstrates a microservices architecture using Spring Boot. Each microservice is independently deployable and communicates with others via REST APIs and Apache Kafka for event-driven communication.</p>
    <p>The project uses:</p>
    <ul>
        <li><strong>MongoDB</strong>: As the primary database for each microservice.</li>
        <li><strong>Apache Kafka</strong>: For asynchronous communication between microservices.</li>
        <li><strong>Prometheus and Grafana</strong>: For monitoring and visualizing metrics.</li>
        <li><strong>Keycloak</strong>: For authentication and authorization.</li>
    </ul>

    <h2 id="prerequisites">Prerequisites</h2>
    <p>Before running the project, ensure you have the following installed:</p>
    <ul>
        <li>Java Development Kit (JDK) 17 or higher</li>
        <li>Maven 3.x</li>
        <li>MongoDB</li>
        <li>Apache Kafka</li>
        <li>Prometheus</li>
        <li>Grafana</li>
        <li>Keycloak</li>
    </ul>

    <h2 id="setup">Setup</h2>
    <p>Follow these steps to set up the project:</p>
    <ol>
        <li>Clone the repository:</li>
        <pre><code>git clone https://github.com/your-username/springboot-microservices.git</code></pre>
        <li>Navigate to each microservice directory and build the project:</li>
        <pre><code>cd product-service
mvn clean install

cd ../inventory-service
mvn clean install

cd ../order-service
mvn clean install</code></pre>
        <li>Configure the MongoDB connection in the <code>application.properties</code> file for each microservice.</li>
        <li>Set up Apache Kafka and ensure it is running. Update the Kafka broker address in the <code>application.properties</code> file for each microservice.</li>
        <li>Configure Keycloak for authentication and update the Keycloak settings in the <code>application.properties</code> file for each microservice.</li>
    </ol>

    <h2 id="running-the-services">Running the Services</h2>
    <p>To run the microservices:</p>
    <ol>
        <li>Start MongoDB and ensure it is running.</li>
        <li>Start Apache Kafka and create the required topics.</li>
        <li>Run each microservice using Maven:</li>
        <pre><code>cd product-service
mvn spring-boot:run

cd ../inventory-service
mvn spring-boot:run

cd ../order-service
mvn spring-boot:run</code></pre>
    </ol>

    <h2 id="api-endpoints">API Endpoints</h2>
    <p>Below are the API endpoints for each microservice:</p>
    <h3>Product Service</h3>
    <ul>
        <li><code>GET /api/products</code>: Get all products.</li>
        <li><code>GET /api/products/{id}</code>: Get a product by ID.</li>
        <li><code>POST /api/products</code>: Create a new product.</li>
        <li><code>PUT /api/products/{id}</code>: Update a product.</li>
        <li><code>DELETE /api/products/{id}</code>: Delete a product.</li>
    </ul>
    <h3>Inventory Service</h3>
    <ul>
        <li><code>GET /api/inventory</code>: Get all inventory items.</li>
        <li><code>GET /api/inventory/{productId}</code>: Get inventory for a specific product.</li>
        <li><code>POST /api/inventory</code>: Add inventory for a product.</li>
        <li><code>PUT /api/inventory/{productId}</code>: Update inventory for a product.</li>
    </ul>
    <h3>Order Service</h3>
    <ul>
        <li><code>GET /api/orders</code>: Get all orders.</li>
        <li><code>GET /api/orders/{id}</code>: Get an order by ID.</li>
        <li><code>POST /api/orders</code>: Create a new order.</li>
        <li><code>PUT /api/orders/{id}</code>: Update an order.</li>
        <li><code>DELETE /api/orders/{id}</code>: Cancel an order.</li>
    </ul>

    <h2 id="monitoring">Monitoring with Grafana and Prometheus</h2>
    <p>To monitor the microservices:</p>
    <ol>
        <li>Set up Prometheus and configure it to scrape metrics from each microservice.</li>
        <li>Set up Grafana and connect it to Prometheus.</li>
        <li>Import pre-configured dashboards or create custom dashboards to visualize metrics.</li>
    </ol>

    <h2 id="authentication">Authentication with Keycloak</h2>
    <p>To secure the microservices using Keycloak:</p>
    <ol>
        <li>Set up a Keycloak server and create a realm.</li>
        <li>Configure clients for each microservice in Keycloak.</li>
        <li>Update the <code>application.properties</code> file for each microservice with the Keycloak settings (realm, client ID, client secret, etc.).</li>
        <li>Use Keycloak to authenticate and authorize API requests.</li>
    </ol>

    <h2 id="contributing">Contributing</h2>
    <p>Contributions are welcome! Please follow these steps:</p>
    <ol>
        <li>Fork the repository.</li>
        <li>Create a new branch for your feature or bugfix.</li>
        <li>Submit a pull request with a detailed description of your changes.</li>
    </ol>

    <h2 id="license">License</h2>
    <p>This project is licensed under the MIT License. See the <a href="LICENSE">LICENSE</a> file for details.</p>
</body>
</html>
