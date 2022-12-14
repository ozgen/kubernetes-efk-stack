# elasticsearch-fluentd-kibana
### EFK Stack on Kubernetes
This repository is an example of how to configure elasticsearch, kibana and fluentd for logging in kubernetes. The repository is inspired from that [blog].

Security is disabled in elasticsearch and kibana. For this scenario, `elasticsearch.yml` file is overwritten by the `configmap.yaml`. 
Also in order to solve parser error in fluentd `FLUENT_CONTAINER_TAIL_PARSER_TYPE` is added to environment variable in the `fluentd/deamonset.yaml`.

## How to Setup?
1 - Create namespace logging : `kubectl create ns logging`

2 - In the project directory:
` kustomize build k8s | kubectl apply -f -
`

Check & port-forwarding the elasticsearch deployed correctly or not ?

Check & port-forwarding the kibana deployed correctly or not ?


## To see the results :
when check all pods work fine, then you can add index pattern in kibana as depicted on this  [blog].
Then the results should be :

In kibana client:

![alt tag](https://github.com/ozgen/elasticsearch-fluentd-kibana/blob/main/result/kibana_result.png)



## Resources

https://devopscube.com/setup-efk-stack-on-kubernetes/

https://www.deepnetwork.com/blog//2020/03/13/password-protected-efk-stack-on-k8s.html

https://www.digitalocean.com/community/tutorials/how-to-set-up-an-elasticsearch-fluentd-and-kibana-efk-logging-stack-on-kubernetes

[blog]: https://devopscube.com/setup-efk-stack-on-kubernetes/
