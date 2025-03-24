# Elasticsearch & Kibana Docker Setup

This repository contains a **Docker Compose** configuration to run **Elasticsearch** and **Kibana** using Docker.

## Prerequisites

Ensure you have the following installed on your system:
- [Docker](https://docs.docker.com/get-docker/)
- [Docker Compose](https://docs.docker.com/compose/install/)

## Services

This setup includes the following services:
1. **Elasticsearch** (v7.17.0) - A distributed search and analytics engine.
2. **Kibana** (v7.17.0) - A visualization tool for Elasticsearch data.

## Setup & Usage

### 1. Clone this repository
```sh
git clone https://github.com/your-username/elasticsearch-kibana-docker.git
cd elasticsearch-kibana-docker
```

### 2. Start the services
Run the following command to start Elasticsearch and Kibana:
```sh
docker-compose up -d
```
This will start the containers in detached mode.

### 3. Access the Services
- **Elasticsearch API**: http://localhost:9200
- **Kibana UI**: http://localhost:5601

### 4. Check Running Containers
To see running containers:
```sh
docker ps
```

### 5. Stop the Services
To stop and remove the containers:
```sh
docker-compose down
```

## Configuration Details
- **Elasticsearch**
  - Runs on port `9200`
  - Uses a single-node discovery mode
  - Memory limit: `512MB`
  
- **Kibana**
  - Runs on port `5601`
  - Connects to Elasticsearch automatically
  
## Persistent Data Storage
Elasticsearch data is stored in a named volume `es_data`, ensuring data persistence even after restarting the containers.

## Network
Both services communicate over a custom Docker network `esnet` using the bridge driver.

## Troubleshooting
- To view logs for Elasticsearch:
  ```sh
  docker logs elasticsearch
  ```
- To view logs for Kibana:
  ```sh
  docker logs kibana
  ```
- If you face memory issues, adjust `ES_JAVA_OPTS` in `docker-compose.yml`.

## License
This project is licensed under the MIT License.

---

Happy coding! 🚀
