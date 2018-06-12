## Rules for US team

---

### Language

golang version >= 1.10

### Framework and Public lib

```
 Development:

 1. https://github.com/jollyburger/xframe (for HTTP-API or Protobuf backend) preferred
 2. https://github.com/grpc/grpc-go (for Protobuf backend) preferred
 3. https://github.com/gin-gonic/gin (for HTTP-API)
 4. others (beego/go-kit/...)

 Lib: (optional)

 1. https://github.com/jollyburger/xmysql (Mysql lib)
 2. https://github.com/jollyburger/xmgo (MongoDB lib)
 3. https://github.com/jollyburger/pets (Zookeeper lib)
 4. https://github.com/Jeffail/tunny (Goroutine pool lib)
 5. others (kafka/tracing/prometheus/redis)

 Debug tool
  
 1. go pprof (for mem-leak or high cpu)
 2. in general, log
 3. jaeger (for request tracing)

 Dependency tool

 1. govendor
 	- govendor init
	- govendor update +external

 Directory structure

 1. main.go (main entry)
 2. app/ (config structure)
 3. examples/ (template.json configuration file)
 4. build/ (for binary)
 5. deploy/ (Dockerfile)
 6. utils/ (internal lib)
 7. logic/ (handlers/algorithms/3rd party methods...)
```

### API rules

#### Common Response

```json
{
	"retcode": "int, e.g 0: success",
	"message": "string, error message",
	"data": "[]bytes json-style, data needed"
}
```

#### Example
```json
{
	10000: "query input error",
	10001: "internal error",
	10002: "data error"	
}
```


#### GET Request

- route: "/${service}/${module}/${action}" or "/${module}/${action}"

- all parameters in lower case, e.g /a/b/c?user_id=d&count=e

#### POST Request

- content-type: application/json

### Protocol in Protobuf

- gRPC(protobuf >= 3.0)

- xframe (protobuf >= 2.0)

### Version/Git management

- Version control
	- refer to https://semver.org/
	- version example Va.b.c

- Git management
	- command: git commit -seav
		- including (optional)
			- new features
			- bug fix
			- optimization
	- after commit, please git tag 
