# Phase 1 – Data Ingestion

## Objective

To securely ingest raw business licensing data into Amazon S3 for further analysis by setting up a cloud storage foundation that supports encryption, versioning, and lifecycle policies.

---

## Tools & Services Used

| AWS Service    | Purpose                                               |
|----------------|--------------------------------------------------------|
| Amazon EC2     | Used as a staging environment to upload files to S3   |
| Amazon S3      | Primary cloud storage for raw and cleaned datasets    |
| AWS KMS        | Applied encryption at rest using a customer-managed key |
| S3 Versioning  | Enabled to track changes and support recovery         |
| S3 Replication | Configured for redundancy (demonstration only)        |

---

## Activities Performed

1. Launched an EC2 instance with permissions to interact with S3.
2. Connected to the instance via SSH to upload two files:
   - `Business-Licences-1997-to-2012.csv`
   - `business-licences-1997-to-2012.json`
3. Created an Amazon S3 bucket for raw data storage.
4. Enabled **SSE-KMS encryption** using a custom KMS key.
5. Turned on **versioning** to retain object history.
6. Configured **replication** from raw bucket to another region (demonstration only).

---

## Folder Structure

Uploaded files were stored in:

