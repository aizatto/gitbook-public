# GCP

* [Mapping AWS to GCP](https://cloud.google.com/free/docs/map-aws-google-cloud-platform)

## Datastore

Being deprecated for Firestore

> [Cloud Firestore](https://cloud.google.com/firestore/) is the next generation of Cloud Datastore.

## Comparisons with AWS

* API Gateway
  * No GCP Equivalent
  * No Custom domains
  * GCP Cloud Functions can be automatically deployed to an endpoint with a flag
* Firestore has better free rates
  * No on-demand/provisioned limitations
* Lambda
  * Need to test async/await
  * Seems you launch individual functions than a group of functions
    * Lambda has "Applications", GCP doesn't seem to have an equivalent way to group
    * Potentially more name clashing
  * Distinct difference between HTTP Triggers and Event Triggers

