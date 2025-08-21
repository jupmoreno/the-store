# The Store
**The Store** is a modern e-commerce platform built with microservices architecture.

Our platform provides a complete shopping experience with:
- **Beautiful storefront** with customizable themes and responsive design
- **Scalable microservices** built with multiple languages and frameworks
- **Real-time inventory management** and order processing

## 🛠️ Development

### Prerequisites
- Docker Desktop running
- Kind (Kubernetes in Docker) installed
- kubectl CLI tool installed

### Cluster Management

Use the `local.sh` script to manage your local Kubernetes cluster:

```bash
# Create a new cluster and deploy all services
./local.sh create-cluster

# Rebuild the entire cluster (delete and recreate)
./local.sh rebuild-cluster

# Delete the cluster
./local.sh delete-cluster

# Check cluster status
./local.sh status

# Build and load Docker images only
./local.sh reload-images
```

After running `./local.sh create-cluster`, access The Store at: **http://localhost**.

### Testing
Run end-to-end tests with Cypress:

```bash
cd e2e
npm install
npm run cypress:open
```

## 🏗️ Architecture

The Store is built with a microservices architecture that uses different technologies:

![Architecture](/docs/images/architecture.png)

| Service | Language | Description |
|---------|----------|-------------|
| [UI](./src/ui/) | Java (Spring Boot) | Modern web interface with themes and chat bot |
| [Catalog](./src/catalog/) | Go | Product catalog API with search and filtering |
| [Cart](./src/cart/) | Java (Spring Boot) | Shopping cart management with Redis/DynamoDB |
| [Orders](./src/orders/) | Java (Spring Boot) | Order processing and management |
| [Checkout](./src/checkout/) | Node.js (NestJS) | Checkout orchestration and payment processing |

---

**The Store** - Built with ❤️ for modern e-commerce
