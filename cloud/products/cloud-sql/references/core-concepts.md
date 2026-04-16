# Cloud SQL Core Concepts

Cloud SQL provides managed relational databases, abstracting the underlying
infrastructure while offering standard database engines.

## Supported Engines

Cloud SQL supports the following database engines (see [supported versions](https://docs.cloud.google.com/sql/docs/db-versions)):

- **MySQL:** Versions 5.6, 5.7, 8.0, and 8.4.

- **PostgreSQL:** Versions 9.6, 10, 11, 12, 13, 14, 15, 16, 17, and 18 (default).

- **SQL Server:** 2017 (Express, Web, Standard, Enterprise), 2019, 2022, and 2025.

## Instance Architecture

Each Cloud SQL instance is powered by a virtual machine (VM) running the
database program.

- **Primary Instance:** The main read/write connection point.

- **High Availability (HA):** Provides a standby VM in a different zone with
  automatic failover.

- **Read Replicas:** Used to scale read traffic and provide local access in
  different regions.

## Storage and Networking

- **Persistent Disk:** Scalable and durable network storage attached to the VM.

- **Connectivity:** Supports Private IP (via VPC peering or Private Service
  Connect) and Public IP (with authorized networks or Auth Proxy).

## Pricing

Cloud SQL pricing is based on:

- **Instance Type:** vCPUs and RAM.

- **Storage:** Amount of data stored and IOPS.

- **Networking:** Network egress and IP address usage.

For the latest pricing, visit: [Cloud SQL Pricing](https://cloud.google.com/sql/pricing).
