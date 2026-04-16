# Cloud SQL Client Libraries

Google Cloud provides client libraries and connectors to simplify connecting to
Cloud SQL from various programming languages.

## Getting Started

Ensure you have the Google Cloud SDK installed and authenticated.
[Install Google Cloud SDK](https://cloud.google.com/sdk/docs/install)

### Language Connectors

The Cloud SQL Language Connectors (Python, Java, Go, Node.js) provide a secure
way to connect without managing IP allowlists or SSL certificates.

#### Python

- **Installation:**

  ```bash
  pip install "cloud-sql-python-connector[pg8000]"
  ```

- **Usage Example:**

  ```python
  from google.cloud.sql.connector import Connector
  connector = Connector()
  def getconn():
      conn = connector.connect(
          "project:region:instance",
          "pg8000",
          user="my-user",
          password="my-password",
          db="my-db"
      )
      return conn
  ```

#### Java

- **Maven Dependency:**

  ```xml
  <dependency>
    <groupId>com.google.cloud</groupId>
    <artifactId>google-cloud-sql-mysql</artifactId>
  </dependency>
  ```

#### Node.js (TypeScript)

- **Installation:**

  ```bash
  npm install @google-cloud/cloud-sql-connector
  ```

#### Go

- **Installation:**

  ```bash
  go get cloud.google.com/go/cloudsqlconn
  ```

## Cloud SQL Admin API

To manage Cloud SQL resources (e.g., list instances) programmatically, use the
`sqladmin` libraries.

- [Cloud SQL Admin API Overview](https://cloud.google.com/sql/docs/mysql/admin-api)
