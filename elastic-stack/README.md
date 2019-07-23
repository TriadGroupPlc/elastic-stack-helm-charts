# Elastic-stack Helm Chart
This chart installs an elasticsearch cluster with kibana and filebeat by default.
You can optionally add logstash and install Fluentd instead if you prefer.

It may or may not work as a traditional Helm chart, we use it to template our Kubernetes resource for an Elastic stack

## Usage
### Get dependencies
Within the elastic-stack directory
    helm dep update

### Template
Fill in your values.yaml and then, move to the top level directory and run the template command:
    cd ..
    helm template -f elk/values.yaml --name <name> elk > outfile.manifest.yaml
    
### (Optional) Create a namespace
Create a namespace.yml file, define a namespace then apply it. Helps to segregate the resources this creates.
    kubectl apply -f namespace.yml

### (Optional) Create certificate secrets
If you're using certificates generate them as you normally would, or using the [Elasticsearch utility](https://www.elastic.co/guide/en/elasticsearch/reference/current/configuring-tls.html)

    kubectl create secret generic <name> --from-file=Certificate.p12

### Deploy the stack
    kuebctl apply -f outfile.manifest.yaml -n <namespace>


### Local access
Once all the pods have started you can expose them temporarily using port forwarding:
```
    kubectl port-forward svc/<elasticsearch service> -n monitoring 9200
    kubectl port-forward svc/<kibana service> -n monitoring 5601
```