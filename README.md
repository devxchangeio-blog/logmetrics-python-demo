## logmetrics-demo

Logmetrics framework provides simplified configuration to log payload for python project.

## Pypi Python Package 
```
https://pypi.org/project/logmetrics-sdk/
```

## Dependencies

```
pip install logmetrics-sdk
	
```

## Usage - Python Flask Projects

### 

```
from logmetrics_sdk.logmetrics import LogMetrics

@app.route('/todo/api/v1/tasks', methods=['GET'])
@LogMetrics
def get_tasks():
    return jsonify(tasks)
	
```

### logmetrics json schema

```
{
  "$schema": "http://json-schema.org/draft-04/schema#",
  "type": "LogMetrics",
  "properties": {
    "Node": {
      "type": "string",
      "description": "Application Host IP Address"
    },
    "message_type": {
      "type": "string",
      "description": "Logmetrics message type",
      "value": "LOGMETRICS_MESSAGE"
    },
    "Duration": {
      "type": "integer",
      "description": "Response time of the API"
    },
    "Host": {
      "type": "string",
      "description": "Application Host Name"
    },
    "Fault": {
      "type": "boolean",
      "description": "API Success or Failed status "
    },
    "Method": {
      "type": "string",
      "description": "API Method name"
    },
    "ResponseBody": {
      "type": "string",
      "description": "API Response Body"
    },
    "StartDateTime": {
      "type": "string",
      "description": "API Start Time"
    },
    "EndDateTime": {
      "type": "string",
      "description": "API End time"
    },
    "HttpMethod": {
      "type": "string",
      "description": "Http Method Type"
    },
    "RequestBody": {
      "type": "string",
      "description": "API Request Body"
    }
  }
}


```

### sample logmetrics message
```
{
  "Node": "127.0.0.1",
  "message_type": "LOGMETRICS_MESSAGE",
  "Duration": 106,
  "Host": "hostname",
  "Fault": false,
  "Method": "/user-service/api/v1/user/{id}",
  "ResponseBody": "{\"id\":1,\"name\":\"02adcec2263d2127269fcd769c33f029\",\"age\":\"35135aaa6cc23891b40cb3f378c53a17a1127210ce60e125ccf03efcfdaec458\",\"salary\":\"********\"}",
  "StartDateTime": "Tue Nov 26 23:22:54 EST 2019",
  "EndDateTime": "Tue Nov 26 23:22:54 EST 2019",
  "HttpMethod": "GET",
  "RequestBody": ""
}
```
