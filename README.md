# Elastic Stack Kubernetes Helm Charts

A slightly tweaked set of helm charts based on the [elastic/helm-charts](https://github.com/elastic/helm-charts) with the additions of Logstash and Fluentd as well as a 
fairly noddy Elastic-stack implementation that groups the other charts.

It may or may not work as a traditional Helm chart, it can be used to template Kubernetes resource for an Elastic stack

See [elastic-stack](./elastic-stack/README.md) for details on how to use the templates and deploy resources.

---

This functionality is in beta and is subject to change. The design and code is less mature than official GA features and is being provided as-is with no warranties. Beta features are not subject to the support SLA of official GA features.

## Charts

Please look in the chart directories for the documentation for each chart. These helm charts are designed to be a lightweight way to configure our official docker images. Links to the relevant docker image documentation has also been added below.

* [Elasticsearch](./elasticsearch/README.md) - [docker image docs](https://www.elastic.co/guide/en/elasticsearch/reference/current/docker.html)
* [Kibana](./kibana/README.md) - [docker image docs](https://www.elastic.co/guide/en/kibana/current/docker.html)
* [Filebeat](./filebeat/README.md) - [docker image docs](https://www.elastic.co/guide/en/beats/filebeat/current/running-on-docker.html)
* [Logstash](./logstash/README.md) - [docker image docs](https://www.elastic.co/guide/en/logstash/current/docker.html)
* [Fluentd](./fluentd/README.md) - [docker image docs](https://github.com/fluent/fluentd-docker-image)

