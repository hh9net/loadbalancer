# loadbalancer

A basic TCP/UDP loadbalancer that can use round robin, hash, and least number of connections mechanisms for proxying to backends. Can also be used for TLS termination. See the sample_configs directory for sample configs.

The loadbalancers config is specified with the '-config' option and can be a path to file or a HTTP URL.

>Inspired by [https://github.com/BlueDragonX/go-proxy-example](https://github.com/BlueDragonX/go-proxy-example)


## Building

```./build.sh```


## Running

#### Create TLS certs
```./make-cert.sh```


#### Start some backends
```./create-backends.sh```


#### Run the loadbalancer
```./builds/linux/lb-0.1 -config sample_configs/config.json```
or
```./builds/linux/lb-0.1 -config http://localhost:8000/config.json```


#### Make a connection
```curl http://localhost:9090```
or for UDP
```dig @127.0.0.1 -p 5053 google.com```


#### Make a connection using TLS
```curl -v --cacert certs/server.pem https://localhost:8443```
