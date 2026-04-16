# Cloud SQL IAM & Security

Cloud SQL uses Identity and Access Management (IAM) to control access to
instances and databases.

## Predefined IAM Roles

| Predefined Role | Usage |
| :--- | :--- |
| `roles/cloudsql.admin` | Full control over all Cloud SQL resources. |
| `roles/cloudsql.editor` | Manage resources; cannot modify IAM or delete
  instances. |
| `roles/cloudsql.viewer` | Read-only access to Cloud SQL resources. |
| `roles/cloudsql.client` | Permission to connect to an instance (required for
  Auth Proxy). |
| `roles/cloudsql.instanceUser` | Permission to log in to a Cloud SQL
  instance. |

## Secure Connectivity

- **Cloud SQL Auth Proxy:** The recommended way to connect securely. It provides
  IAM-based authentication and end-to-end encryption without requiring SSL
  certificates or authorized networks.

- **Private IP:** Use VPC peering or Private Service Connect (PSC) to keep
  database traffic within the Google Cloud network.

- **Authorized Networks:** If using Public IP, restrict access to specific CIDR
  ranges.

## Data Security

- **Encryption at Rest:** All data is encrypted by default. Use
  Customer-Managed Encryption Keys (CMEK) for additional control.

- **IAM Database Authentication:** Authenticate to the database using IAM users
  or service accounts instead of static passwords (available for MySQL and
  PostgreSQL).

## Service Accounts

- **Service Identity:** Cloud SQL uses an instance service account
  (`p[PROJECT_NUMBER]-[UNIQUE_ID]@gcp-sa-cloud-sql.iam.gserviceaccount.com`)
  for tasks like writing backups to Cloud Storage. Service agent accounts
  (`service-PROJECT_NUMBER@gcp-sa-cloud-sql.iam.gserviceaccount.com`) are used
  only for internal management tasks.

- **App Connectivity:** Grant the service account running your app (e.g., on
  Cloud Run or GKE) the `roles/cloudsql.client` role.

For more information, see:
[Cloud SQL Security Overview](https://cloud.google.com/sql/docs/mysql/security).
