# Gcloud Cheat Sheet

1. Authentication & Configuration
    ``` bash
    # Authenticate with Google Cloud
    gcloud auth login

    # Set default project
    gcloud config set project PROJECT_ID

    # List active configurations
    gcloud config configurations list

    # Activate a specific configuration
    gcloud config configurations activate CONFIG_NAME


    ```
2. Compute Engine
    ``` bash 
    # List VM instances
    gcloud compute instances list

    # Create a new VM instance
    gcloud compute instances create INSTANCE_NAME --zone=ZONE

    # SSH into a VM instance
    gcloud compute ssh INSTANCE_NAME --zone=ZONE

    # Stop a VM instance
    gcloud compute instances stop INSTANCE_NAME --zone=ZONE

    # Delete a VM instance
    gcloud compute instances delete INSTANCE_NAME --zone=ZONE
    ```
3. Kubernetes Engine (GKE)
``` bash
# List Kubernetes clusters
gcloud container clusters list

# Create a Kubernetes cluster
gcloud container clusters create CLUSTER_NAME --zone=ZONE

# Get credentials for a cluster
gcloud container clusters get-credentials CLUSTER_NAME --zone=ZONE

# Delete a Kubernetes cluster
gcloud container clusters delete CLUSTER_NAME --zone=ZONE
```
4. Cloud Storage
```bash
# List buckets
gcloud storage buckets list

# Create a bucket
gcloud storage buckets create BUCKET_NAME --location=REGION

# Upload a file to a bucket
gcloud storage cp FILE_PATH gs://BUCKET_NAME/

# Download a file from a bucket
gcloud storage cp gs://BUCKET_NAME/FILE_NAME FILE_PATH

# Delete a bucket
gcloud storage buckets delete BUCKET_NAME
```
5. Cloud Functions
``` bash
# List Cloud Functions
gcloud functions list

# Deploy a Cloud Function
gcloud functions deploy FUNCTION_NAME --runtime=RUNTIME --trigger-http --entry-point=ENTRY_POINT

# Call a Cloud Function
gcloud functions call FUNCTION_NAME --data='{"key":"value"}'

# Delete a Cloud Function
gcloud functions delete FUNCTION_NAME
```
6. Cloud Run
``` bash 
# List Cloud Run services
gcloud run services list

# Deploy to Cloud Run
gcloud run deploy SERVICE_NAME --image=IMAGE_URL --region=REGION

# Delete a Cloud Run service
gcloud run services delete SERVICE_NAME
```
7. Cloud SQL
```bash
# List Cloud SQL instances
gcloud sql instances list

# Create a Cloud SQL instance
gcloud sql instances create INSTANCE_NAME --tier=TIER --region=REGION

# Connect to a Cloud SQL instance
gcloud sql connect INSTANCE_NAME --user=USERNAME

# Delete a Cloud SQL instance
gcloud sql instances delete INSTANCE_NAME
``` 
8. IAM (Identity and Access Management)
``` bash
# List IAM roles
gcloud iam roles list

# Add an IAM policy binding
gcloud projects add-iam-policy-binding PROJECT_ID \
  --member=MEMBER \
  --role=ROLE

# Remove an IAM policy binding
gcloud projects remove-iam-policy-binding PROJECT_ID \
  --member=MEMBER \
  --role=ROLE
``` 
9. Pub/Sub
```bash
# List Pub/Sub topics
gcloud pubsub topics list

# Create a Pub/Sub topic
gcloud pubsub topics create TOPIC_NAME

# Publish a message to a topic
gcloud pubsub topics publish TOPIC_NAME --message="Hello, world!"

# Delete a Pub/Sub topic
gcloud pubsub topics delete TOPIC_NAME
``` 
10. BigQuery
``` bash
# List datasets
gcloud bigquery datasets list

# Create a dataset
gcloud bigquery datasets create DATASET_NAME

# Query a dataset
gcloud bigquery query 'SELECT * FROM `PROJECT_ID.DATASET.TABLE` LIMIT 10'

# Delete a dataset
gcloud bigquery datasets delete DATASET_NAME
``` 
11. Networking
``` bash
# List VPC networks
gcloud compute networks list

# Create a VPC network
gcloud compute networks create NETWORK_NAME --subnet-mode=auto

# Delete a VPC network
gcloud compute networks delete NETWORK_NAME
```
12. Logs & Monitoring
``` bash
# List log entries
gcloud logging read "logName:projects/PROJECT_ID/logs/LOG_ID"

# Write a custom log entry
gcloud logging write LOG_NAME "This is a log message."

# View metrics
gcloud monitoring metrics list
```