# elasticsearch_sizing_aws_vs_saas

### Inputs: 
Calculate monthly/yearly TCO of Production HA elasticsearch/opensearch cluster to support centralized log collection with 30-60days retention and monthky 150gb of logs.
Monthly ingest:150Gb
Daily log ingest: 2Gb
RPS average(RPS): 50
RPS peak: <tbc>
Retention period: 30days for 99% (149.81Gb), 60 days for 1% (180mb)
Peak ingest atemtps: 1m mobile apps trying to ship logs in json format through API
Retries and Exponentila back-off is implemented in mobile client
Bulk shipment: logs lines are accamulated and shipped once 1000 lines (configurable)
usage type: write-heavy, ocassional searches through Kibana/API
FTE Hourly rate: $31.25
Data Loss - unacceptable
Periodic maintenance up to 3-4h/month is ok


### Considered Options (2022):
1. AWS OpenSearch managed service 
2. Self-Hosted Elasticsearch cluster on AWS EC2 instances
3. Logz.io SaaS
4. Self-Hosted k8s cluster with Elastic CLoud on Kubernetes operator https://github.com/elastic/cloud-on-k8s
5. Elastic.cloud SaaS.

