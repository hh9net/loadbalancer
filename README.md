# loadbalancer

A basic TCP loadbalancer that can use round robin, hash, and least number of connections mechanisms for proxying to backends. Can also be used for TLS termination. See the sample_configs directory for sample configs.

The loadbalancers config is specified with the '-config' option and can be a path to file or a HTTP URL.

Inspired by [https://github.com/BlueDragonX/go-proxy-example](https://github.com/BlueDragonX/go-proxy-example)


## Building

```make build```


## Running

#### Create TLS certs
```./make-cert.sh```


#### Start some backends
```./create-backends.sh```


#### Run the loadbalancer
```./loadbalancer -config sample_configs/config.json```
```./loadbalancer -config http://localhost:8000/least_conn.json```


#### Make a connection
```curl -v http://localhost:9090```


#### Make a connection using TLS
```curl -v --cacert certs/server.pem https://localhost:8080```
