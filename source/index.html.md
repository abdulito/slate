---
title: Lattice API Docs
language_tabs:
  - shell: Shell
  - http: HTTP
  - javascript: JavaScript
  - javascript--nodejs: Node.JS
  - ruby: Ruby
  - python: Python
  - java: Java
  - go: Go
toc_footers: []
includes: []
search: true
highlight_theme: darkula
headingLevel: 2

---

<h1 id="Lattice-API-Docs">Lattice API Docs v1.0</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

This document describes the lattice API.

Base URLs:

* <a href="//localhost:8876/v1">//localhost:8876/v1</a>

<a href="TBD">Terms of service</a>

 License: Apache 2.0

# Authentication

* API Key (ApiKeyAuth)
    - Parameter Name: **apiKey**, in: header. 

<h1 id="Lattice-API-Docs-builds">builds</h1>

## list-builds

<a id="opIdlist-builds"></a>

> Code samples

```shell
# You can also use wget
curl -X GET //localhost:8876/v1/systems/{system}/builds \
  -H 'Accept: application/json'

```

```http
GET //localhost:8876/v1/systems/{system}/builds HTTP/1.1
Host: null

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '//localhost:8876/v1/systems/{system}/builds',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('//localhost:8876/v1/systems/{system}/builds',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '//localhost:8876/v1/systems/{system}/builds',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('//localhost:8876/v1/systems/{system}/builds', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("//localhost:8876/v1/systems/{system}/builds");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "//localhost:8876/v1/systems/{system}/builds", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /systems/{system}/builds`

*Lists builds*

list builds

<h3 id="list-builds-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|system|path|string|true|System ID|

> Example responses

> 200 Response

```json
[
  {
    "completionTimestamp": "string",
    "id": "string",
    "services": {},
    "startTimestamp": "string",
    "state": "string",
    "version": "string"
  }
]
```

<h3 id="list-builds-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|

<h3 id="list-builds-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[v1.Build](#schemav1.build)]|false|none|none|
|» completionTimestamp|string|false|none|Completion timestamp|
|» id|string|false|none|ID|
|» services|object|false|none|Services maps service paths (e.g. /foo/bar/buzz) to the status of the build for that service in the Build.|
|» startTimestamp|string|false|none|Start timestamp|
|» state|string|false|none|State|
|» version|string|false|none|Version|

<aside class="success">
This operation does not require authentication
</aside>

## build-system

<a id="opIdbuild-system"></a>

> Code samples

```shell
# You can also use wget
curl -X POST //localhost:8876/v1/systems/{system}/builds \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST //localhost:8876/v1/systems/{system}/builds HTTP/1.1
Host: null
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: '//localhost:8876/v1/systems/{system}/builds',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "version": {}
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('//localhost:8876/v1/systems/{system}/builds',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.post '//localhost:8876/v1/systems/{system}/builds',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('//localhost:8876/v1/systems/{system}/builds', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("//localhost:8876/v1/systems/{system}/builds");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "//localhost:8876/v1/systems/{system}/builds", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /systems/{system}/builds`

*Build system*

build system

> Body parameter

```json
{
  "version": {}
}
```

<h3 id="build-system-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|system|path|string|true|System ID|
|body|body|[rest.BuildRequest](#schemarest.buildrequest)|true|Create build|

> Example responses

> 200 Response

```json
{
  "completionTimestamp": "string",
  "id": "string",
  "services": {},
  "startTimestamp": "string",
  "state": "string",
  "version": "string"
}
```

<h3 id="build-system-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[v1.Build](#schemav1.build)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[v1.ErrorResponse](#schemav1.errorresponse)|

<aside class="success">
This operation does not require authentication
</aside>

## get-build

<a id="opIdget-build"></a>

> Code samples

```shell
# You can also use wget
curl -X GET //localhost:8876/v1/systems/{system}/builds/{id} \
  -H 'Accept: application/json'

```

```http
GET //localhost:8876/v1/systems/{system}/builds/{id} HTTP/1.1
Host: null

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '//localhost:8876/v1/systems/{system}/builds/{id}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('//localhost:8876/v1/systems/{system}/builds/{id}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '//localhost:8876/v1/systems/{system}/builds/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('//localhost:8876/v1/systems/{system}/builds/{id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("//localhost:8876/v1/systems/{system}/builds/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "//localhost:8876/v1/systems/{system}/builds/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /systems/{system}/builds/{id}`

*Get build*

get build

<h3 id="get-build-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|system|path|string|true|System ID|
|id|path|string|true|Build ID|

> Example responses

> 200 Response

```json
{
  "completionTimestamp": "string",
  "id": "string",
  "services": {},
  "startTimestamp": "string",
  "state": "string",
  "version": "string"
}
```

<h3 id="get-build-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[v1.Build](#schemav1.build)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[v1.ErrorResponse](#schemav1.errorresponse)|

<aside class="success">
This operation does not require authentication
</aside>

## get-build-logs

<a id="opIdget-build-logs"></a>

> Code samples

```shell
# You can also use wget
curl -X GET //localhost:8876/v1/systems/{system}/builds/{id}/logs?path=string \
  -H 'Accept: application/json'

```

```http
GET //localhost:8876/v1/systems/{system}/builds/{id}/logs?path=string HTTP/1.1
Host: null

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '//localhost:8876/v1/systems/{system}/builds/{id}/logs',
  method: 'get',
  data: '?path=string',
  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('//localhost:8876/v1/systems/{system}/builds/{id}/logs?path=string',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '//localhost:8876/v1/systems/{system}/builds/{id}/logs',
  params: {
  'path' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('//localhost:8876/v1/systems/{system}/builds/{id}/logs', params={
  'path': 'string'
}, headers = headers)

print r.json()

```

```java
URL obj = new URL("//localhost:8876/v1/systems/{system}/builds/{id}/logs?path=string");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "//localhost:8876/v1/systems/{system}/builds/{id}/logs", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /systems/{system}/builds/{id}/logs`

*Get build logs*

get logs

<h3 id="get-build-logs-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|system|path|string|true|System ID|
|id|path|string|true|Build ID|
|path|query|string|true|Node Path|
|sidecar|query|string|false|Sidecar|
|follow|query|string|false|Follow|
|previous|query|boolean|false|Previous|
|timestamps|query|boolean|false|Timestamps|
|tail|query|integer|false|tail|
|since|query|string|false|Since|
|sinceTime|query|string|false|Since Time|

> Example responses

> 200 Response

```json
"string"
```

<h3 id="get-build-logs-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|log stream|string|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[v1.ErrorResponse](#schemav1.errorresponse)|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="Lattice-API-Docs-deploys">deploys</h1>

## list-deploys

<a id="opIdlist-deploys"></a>

> Code samples

```shell
# You can also use wget
curl -X GET //localhost:8876/v1/systems/{system}/deploys \
  -H 'Accept: application/json'

```

```http
GET //localhost:8876/v1/systems/{system}/deploys HTTP/1.1
Host: null

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '//localhost:8876/v1/systems/{system}/deploys',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('//localhost:8876/v1/systems/{system}/deploys',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '//localhost:8876/v1/systems/{system}/deploys',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('//localhost:8876/v1/systems/{system}/deploys', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("//localhost:8876/v1/systems/{system}/deploys");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "//localhost:8876/v1/systems/{system}/deploys", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /systems/{system}/deploys`

*Lists deploys*

list deploys

<h3 id="list-deploys-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|system|path|string|true|System ID|

> Example responses

> 200 Response

```json
[
  {
    "buildId": "string",
    "id": "string",
    "state": "string"
  }
]
```

<h3 id="list-deploys-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|

<h3 id="list-deploys-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[v1.Deploy](#schemav1.deploy)]|false|none|none|
|» buildId|string|false|none|Build ID|
|» id|string|false|none|ID|
|» state|string|false|none|State|

<aside class="success">
This operation does not require authentication
</aside>

## deploy-system

<a id="opIddeploy-system"></a>

> Code samples

```shell
# You can also use wget
curl -X POST //localhost:8876/v1/systems/{system}/deploys \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST //localhost:8876/v1/systems/{system}/deploys HTTP/1.1
Host: null
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: '//localhost:8876/v1/systems/{system}/deploys',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "buildId": "string",
  "version": {}
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('//localhost:8876/v1/systems/{system}/deploys',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.post '//localhost:8876/v1/systems/{system}/deploys',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('//localhost:8876/v1/systems/{system}/deploys', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("//localhost:8876/v1/systems/{system}/deploys");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "//localhost:8876/v1/systems/{system}/deploys", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /systems/{system}/deploys`

*Deploy system*

build system

> Body parameter

```json
{
  "buildId": "string",
  "version": {}
}
```

<h3 id="deploy-system-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|system|path|string|true|System ID|
|body|body|[rest.DeployRequest](#schemarest.deployrequest)|true|Create deploy|

> Example responses

> 200 Response

```json
{
  "buildId": "string",
  "id": "string",
  "state": "string"
}
```

<h3 id="deploy-system-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[v1.Deploy](#schemav1.deploy)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[v1.ErrorResponse](#schemav1.errorresponse)|

<aside class="success">
This operation does not require authentication
</aside>

## get-deploy

<a id="opIdget-deploy"></a>

> Code samples

```shell
# You can also use wget
curl -X GET //localhost:8876/v1/systems/{system}/deploys/{id} \
  -H 'Accept: application/json'

```

```http
GET //localhost:8876/v1/systems/{system}/deploys/{id} HTTP/1.1
Host: null

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '//localhost:8876/v1/systems/{system}/deploys/{id}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('//localhost:8876/v1/systems/{system}/deploys/{id}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '//localhost:8876/v1/systems/{system}/deploys/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('//localhost:8876/v1/systems/{system}/deploys/{id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("//localhost:8876/v1/systems/{system}/deploys/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "//localhost:8876/v1/systems/{system}/deploys/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /systems/{system}/deploys/{id}`

*Get deploy*

get deploy

<h3 id="get-deploy-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|system|path|string|true|System ID|
|id|path|string|true|Deploy ID|

> Example responses

> 200 Response

```json
{
  "buildId": "string",
  "id": "string",
  "state": "string"
}
```

<h3 id="get-deploy-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[v1.Deploy](#schemav1.deploy)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[v1.ErrorResponse](#schemav1.errorresponse)|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="Lattice-API-Docs-jobs">jobs</h1>

## list-jobs

<a id="opIdlist-jobs"></a>

> Code samples

```shell
# You can also use wget
curl -X GET //localhost:8876/v1/systems/{system}/jobs \
  -H 'Accept: application/json'

```

```http
GET //localhost:8876/v1/systems/{system}/jobs HTTP/1.1
Host: null

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '//localhost:8876/v1/systems/{system}/jobs',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('//localhost:8876/v1/systems/{system}/jobs',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '//localhost:8876/v1/systems/{system}/jobs',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('//localhost:8876/v1/systems/{system}/jobs', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("//localhost:8876/v1/systems/{system}/jobs");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "//localhost:8876/v1/systems/{system}/jobs", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /systems/{system}/jobs`

*Lists jobs*

list jobs

<h3 id="list-jobs-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|system|path|string|true|System ID|

> Example responses

> 200 Response

```json
[
  {
    "completionTimestamp": "string",
    "id": "string",
    "path": "string",
    "startTimestamp": "string",
    "state": "string"
  }
]
```

<h3 id="list-jobs-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|

<h3 id="list-jobs-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[v1.Job](#schemav1.job)]|false|none|none|
|» completionTimestamp|string|false|none|none|
|» id|string|false|none|none|
|» path|string|false|none|none|
|» startTimestamp|string|false|none|none|
|» state|string|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## get-job

<a id="opIdget-job"></a>

> Code samples

```shell
# You can also use wget
curl -X GET //localhost:8876/v1/systems/{system}/jobs/{id} \
  -H 'Accept: application/json'

```

```http
GET //localhost:8876/v1/systems/{system}/jobs/{id} HTTP/1.1
Host: null

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '//localhost:8876/v1/systems/{system}/jobs/{id}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('//localhost:8876/v1/systems/{system}/jobs/{id}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '//localhost:8876/v1/systems/{system}/jobs/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('//localhost:8876/v1/systems/{system}/jobs/{id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("//localhost:8876/v1/systems/{system}/jobs/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "//localhost:8876/v1/systems/{system}/jobs/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /systems/{system}/jobs/{id}`

*Get job*

get job

<h3 id="get-job-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|system|path|string|true|System ID|
|id|path|string|true|Job ID|

> Example responses

> 200 Response

```json
{
  "completionTimestamp": "string",
  "id": "string",
  "path": "string",
  "startTimestamp": "string",
  "state": "string"
}
```

<h3 id="get-job-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[v1.Job](#schemav1.job)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[v1.ErrorResponse](#schemav1.errorresponse)|

<aside class="success">
This operation does not require authentication
</aside>

## get-job-logs

<a id="opIdget-job-logs"></a>

> Code samples

```shell
# You can also use wget
curl -X GET //localhost:8876/v1/systems/{system}/jobs/{id}/logs \
  -H 'Accept: application/json'

```

```http
GET //localhost:8876/v1/systems/{system}/jobs/{id}/logs HTTP/1.1
Host: null

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '//localhost:8876/v1/systems/{system}/jobs/{id}/logs',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('//localhost:8876/v1/systems/{system}/jobs/{id}/logs',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '//localhost:8876/v1/systems/{system}/jobs/{id}/logs',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('//localhost:8876/v1/systems/{system}/jobs/{id}/logs', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("//localhost:8876/v1/systems/{system}/jobs/{id}/logs");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "//localhost:8876/v1/systems/{system}/jobs/{id}/logs", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /systems/{system}/jobs/{id}/logs`

*Get job logs*

get job logs

<h3 id="get-job-logs-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|system|path|string|true|System ID|
|id|path|string|true|Job ID|
|sidecar|query|string|false|Sidecar|
|follow|query|string|false|Follow|
|previous|query|boolean|false|Previous|
|timestamps|query|boolean|false|Timestamps|
|tail|query|integer|false|tail|
|since|query|string|false|Since|
|sinceTime|query|string|false|Since Time|

> Example responses

> 200 Response

```json
"string"
```

<h3 id="get-job-logs-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|log stream|string|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[v1.ErrorResponse](#schemav1.errorresponse)|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="Lattice-API-Docs-node-pools">node-pools</h1>

## list-node-pools

<a id="opIdlist-node-pools"></a>

> Code samples

```shell
# You can also use wget
curl -X GET //localhost:8876/v1/systems/{system}/node-pools \
  -H 'Accept: application/json'

```

```http
GET //localhost:8876/v1/systems/{system}/node-pools HTTP/1.1
Host: null

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '//localhost:8876/v1/systems/{system}/node-pools',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('//localhost:8876/v1/systems/{system}/node-pools',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '//localhost:8876/v1/systems/{system}/node-pools',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('//localhost:8876/v1/systems/{system}/node-pools', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("//localhost:8876/v1/systems/{system}/node-pools");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "//localhost:8876/v1/systems/{system}/node-pools", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /systems/{system}/node-pools`

*Lists node pools*

list node pools

<h3 id="list-node-pools-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|system|path|string|true|System ID|

> Example responses

> 200 Response

```json
[
  {
    "failure_info": {
      "message": "string",
      "time": "string"
    },
    "id": "string",
    "instanceType": "string",
    "numInstances": 0,
    "path": "string",
    "state": "string"
  }
]
```

<h3 id="list-node-pools-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|

<h3 id="list-node-pools-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[v1.NodePool](#schemav1.nodepool)]|false|none|none|
|» failure_info|[v1.NodePoolFailureInfo](#schemav1.nodepoolfailureinfo)|false|none|none|
|»» message|string|false|none|none|
|»» time|string|false|none|none|
|» id|string|false|none|none|
|» instanceType|string|false|none|FIXME: how to deal with epochs?|
|» numInstances|integer|false|none|none|
|» path|string|false|none|none|
|» state|string|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## get-node-pool

<a id="opIdget-node-pool"></a>

> Code samples

```shell
# You can also use wget
curl -X GET //localhost:8876/v1/systems/{system}/node-pools/{id} \
  -H 'Accept: application/json'

```

```http
GET //localhost:8876/v1/systems/{system}/node-pools/{id} HTTP/1.1
Host: null

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '//localhost:8876/v1/systems/{system}/node-pools/{id}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('//localhost:8876/v1/systems/{system}/node-pools/{id}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '//localhost:8876/v1/systems/{system}/node-pools/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('//localhost:8876/v1/systems/{system}/node-pools/{id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("//localhost:8876/v1/systems/{system}/node-pools/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "//localhost:8876/v1/systems/{system}/node-pools/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /systems/{system}/node-pools/{id}`

*Get node pool*

get node pool

<h3 id="get-node-pool-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|system|path|string|true|System ID|
|id|path|string|true|NodePool ID|

> Example responses

> 200 Response

```json
{
  "failure_info": {
    "message": "string",
    "time": "string"
  },
  "id": "string",
  "instanceType": "string",
  "numInstances": 0,
  "path": "string",
  "state": "string"
}
```

<h3 id="get-node-pool-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[v1.NodePool](#schemav1.nodepool)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[v1.ErrorResponse](#schemav1.errorresponse)|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="Lattice-API-Docs-secrets">secrets</h1>

## list-secrets

<a id="opIdlist-secrets"></a>

> Code samples

```shell
# You can also use wget
curl -X GET //localhost:8876/v1/systems/{system}/secrets \
  -H 'Accept: application/json'

```

```http
GET //localhost:8876/v1/systems/{system}/secrets HTTP/1.1
Host: null

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '//localhost:8876/v1/systems/{system}/secrets',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('//localhost:8876/v1/systems/{system}/secrets',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '//localhost:8876/v1/systems/{system}/secrets',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('//localhost:8876/v1/systems/{system}/secrets', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("//localhost:8876/v1/systems/{system}/secrets");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "//localhost:8876/v1/systems/{system}/secrets", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /systems/{system}/secrets`

*Lists secrets*

list secrets

<h3 id="list-secrets-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|system|path|string|true|System ID|

> Example responses

> 200 Response

```json
[
  {
    "name": "string",
    "path": "string",
    "value": "string"
  }
]
```

<h3 id="list-secrets-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|

<h3 id="list-secrets-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[v1.Secret](#schemav1.secret)]|false|none|none|
|» name|string|false|none|none|
|» path|string|false|none|none|
|» value|string|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## set-secret

<a id="opIdset-secret"></a>

> Code samples

```shell
# You can also use wget
curl -X POST //localhost:8876/v1/systems/{system}/secrets \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST //localhost:8876/v1/systems/{system}/secrets HTTP/1.1
Host: null
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: '//localhost:8876/v1/systems/{system}/secrets',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "value": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('//localhost:8876/v1/systems/{system}/secrets',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.post '//localhost:8876/v1/systems/{system}/secrets',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('//localhost:8876/v1/systems/{system}/secrets', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("//localhost:8876/v1/systems/{system}/secrets");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "//localhost:8876/v1/systems/{system}/secrets", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /systems/{system}/secrets`

*set secret*

set secret

> Body parameter

```json
{
  "value": "string"
}
```

<h3 id="set-secret-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|system|path|string|true|System ID|
|body|body|[rest.SetSecretRequest](#schemarest.setsecretrequest)|true|Create secret|

> Example responses

> 200 Response

```json
{
  "name": "string",
  "path": "string",
  "value": "string"
}
```

<h3 id="set-secret-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[v1.Secret](#schemav1.secret)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[v1.ErrorResponse](#schemav1.errorresponse)|

<aside class="success">
This operation does not require authentication
</aside>

## delete-system

<a id="opIddelete-system"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE //localhost:8876/v1/systems/{system}/secrets/{secret} \
  -H 'Accept: application/json'

```

```http
DELETE //localhost:8876/v1/systems/{system}/secrets/{secret} HTTP/1.1
Host: null

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '//localhost:8876/v1/systems/{system}/secrets/{secret}',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('//localhost:8876/v1/systems/{system}/secrets/{secret}',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.delete '//localhost:8876/v1/systems/{system}/secrets/{secret}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('//localhost:8876/v1/systems/{system}/secrets/{secret}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("//localhost:8876/v1/systems/{system}/secrets/{secret}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "//localhost:8876/v1/systems/{system}/secrets/{secret}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /systems/{system}/secrets/{secret}`

*Delete system*

get system

<h3 id="delete-system-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|system|path|string|true|System ID|
|secret|path|string|true|Secret Path|

> Example responses

> 200 Response

```json
{}
```

<h3 id="delete-system-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[v1.Result](#schemav1.result)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[v1.ErrorResponse](#schemav1.errorresponse)|

<aside class="success">
This operation does not require authentication
</aside>

## get-secret

<a id="opIdget-secret"></a>

> Code samples

```shell
# You can also use wget
curl -X GET //localhost:8876/v1/systems/{system}/secrets/{secret} \
  -H 'Accept: application/json'

```

```http
GET //localhost:8876/v1/systems/{system}/secrets/{secret} HTTP/1.1
Host: null

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '//localhost:8876/v1/systems/{system}/secrets/{secret}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('//localhost:8876/v1/systems/{system}/secrets/{secret}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '//localhost:8876/v1/systems/{system}/secrets/{secret}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('//localhost:8876/v1/systems/{system}/secrets/{secret}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("//localhost:8876/v1/systems/{system}/secrets/{secret}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "//localhost:8876/v1/systems/{system}/secrets/{secret}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /systems/{system}/secrets/{secret}`

*Get secret*

get secret

<h3 id="get-secret-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|system|path|string|true|System ID|
|secret|path|string|true|Secret Path|

> Example responses

> 200 Response

```json
{
  "name": "string",
  "path": "string",
  "value": "string"
}
```

<h3 id="get-secret-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[v1.Secret](#schemav1.secret)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[v1.ErrorResponse](#schemav1.errorresponse)|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="Lattice-API-Docs-services">services</h1>

## list-services

<a id="opIdlist-services"></a>

> Code samples

```shell
# You can also use wget
curl -X GET //localhost:8876/v1/systems/{system}/services \
  -H 'Accept: application/json'

```

```http
GET //localhost:8876/v1/systems/{system}/services HTTP/1.1
Host: null

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '//localhost:8876/v1/systems/{system}/services',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('//localhost:8876/v1/systems/{system}/services',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '//localhost:8876/v1/systems/{system}/services',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('//localhost:8876/v1/systems/{system}/services', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("//localhost:8876/v1/systems/{system}/services");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "//localhost:8876/v1/systems/{system}/services", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /systems/{system}/services`

*Lists services*

list services

<h3 id="list-services-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|system|path|string|true|System ID|

> Example responses

> 200 Response

```json
[
  {
    "availableInstances": 0,
    "failureInfo": {
      "message": "string",
      "time": "string"
    },
    "id": "string",
    "instances": [
      "string"
    ],
    "message": "string",
    "path": "string",
    "ports": {},
    "staleInstances": 0,
    "state": "string",
    "terminatingInstances": 0,
    "updatedInstances": 0
  }
]
```

<h3 id="list-services-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|

<h3 id="list-services-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[v1.Service](#schemav1.service)]|false|none|none|
|» availableInstances|integer|false|none|none|
|» failureInfo|[v1.ServiceFailureInfo](#schemav1.servicefailureinfo)|false|none|none|
|»» message|string|false|none|none|
|»» time|string|false|none|none|
|» id|string|false|none|none|
|» instances|[string]|false|none|none|
|» message|string|false|none|none|
|» path|string|false|none|none|
|» ports|object|false|none|none|
|» staleInstances|integer|false|none|none|
|» state|string|false|none|none|
|» terminatingInstances|integer|false|none|none|
|» updatedInstances|integer|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## get-service

<a id="opIdget-service"></a>

> Code samples

```shell
# You can also use wget
curl -X GET //localhost:8876/v1/systems/{system}/services/{id} \
  -H 'Accept: application/json'

```

```http
GET //localhost:8876/v1/systems/{system}/services/{id} HTTP/1.1
Host: null

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '//localhost:8876/v1/systems/{system}/services/{id}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('//localhost:8876/v1/systems/{system}/services/{id}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '//localhost:8876/v1/systems/{system}/services/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('//localhost:8876/v1/systems/{system}/services/{id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("//localhost:8876/v1/systems/{system}/services/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "//localhost:8876/v1/systems/{system}/services/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /systems/{system}/services/{id}`

*Get service*

get service

<h3 id="get-service-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|system|path|string|true|System ID|
|id|path|string|true|Service ID|

> Example responses

> 200 Response

```json
{
  "availableInstances": 0,
  "failureInfo": {
    "message": "string",
    "time": "string"
  },
  "id": "string",
  "instances": [
    "string"
  ],
  "message": "string",
  "path": "string",
  "ports": {},
  "staleInstances": 0,
  "state": "string",
  "terminatingInstances": 0,
  "updatedInstances": 0
}
```

<h3 id="get-service-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[v1.Service](#schemav1.service)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[v1.ErrorResponse](#schemav1.errorresponse)|

<aside class="success">
This operation does not require authentication
</aside>

## get-service-logs

<a id="opIdget-service-logs"></a>

> Code samples

```shell
# You can also use wget
curl -X GET //localhost:8876/v1/systems/{system}/services/{id}/logs?instance=string \
  -H 'Accept: application/json'

```

```http
GET //localhost:8876/v1/systems/{system}/services/{id}/logs?instance=string HTTP/1.1
Host: null

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '//localhost:8876/v1/systems/{system}/services/{id}/logs',
  method: 'get',
  data: '?instance=string',
  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('//localhost:8876/v1/systems/{system}/services/{id}/logs?instance=string',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '//localhost:8876/v1/systems/{system}/services/{id}/logs',
  params: {
  'instance' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('//localhost:8876/v1/systems/{system}/services/{id}/logs', params={
  'instance': 'string'
}, headers = headers)

print r.json()

```

```java
URL obj = new URL("//localhost:8876/v1/systems/{system}/services/{id}/logs?instance=string");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "//localhost:8876/v1/systems/{system}/services/{id}/logs", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /systems/{system}/services/{id}/logs`

*Get service logs*

get service logs

<h3 id="get-service-logs-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|system|path|string|true|System ID|
|id|path|string|true|Service ID|
|instance|query|string|true|Instance|
|sidecar|query|string|false|Sidecar|
|follow|query|string|false|Follow|
|previous|query|boolean|false|Previous|
|timestamps|query|boolean|false|Timestamps|
|tail|query|integer|false|tail|
|since|query|string|false|Since|
|sinceTime|query|string|false|Since Time|

> Example responses

> 200 Response

```json
"string"
```

<h3 id="get-service-logs-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|log stream|string|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[v1.ErrorResponse](#schemav1.errorresponse)|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="Lattice-API-Docs-systems">systems</h1>

## list-systems

<a id="opIdlist-systems"></a>

> Code samples

```shell
# You can also use wget
curl -X GET //localhost:8876/v1/systems \
  -H 'Accept: application/json'

```

```http
GET //localhost:8876/v1/systems HTTP/1.1
Host: null

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '//localhost:8876/v1/systems',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('//localhost:8876/v1/systems',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '//localhost:8876/v1/systems',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('//localhost:8876/v1/systems', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("//localhost:8876/v1/systems");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "//localhost:8876/v1/systems", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /systems`

*List systems*

List systems

> Example responses

> 200 Response

```json
[
  {
    "definitionUrl": "git://github.com/foo/foo.git",
    "id": "string",
    "services": {},
    "state": "string"
  }
]
```

<h3 id="list-systems-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|

<h3 id="list-systems-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[v1.System](#schemav1.system)]|false|none|none|
|» definitionUrl|string|false|none|git url for for where the definition lives in|
|» id|string|false|none|System ID|
|» services|object|false|none|map for service path and services currently running in the system|
|» state|string|false|none|State. One of (pending, failed, deleting, stable, degraded, scaling, updating)|

<aside class="success">
This operation does not require authentication
</aside>

## create-system

<a id="opIdcreate-system"></a>

> Code samples

```shell
# You can also use wget
curl -X POST //localhost:8876/v1/systems \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST //localhost:8876/v1/systems HTTP/1.1
Host: null
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: '//localhost:8876/v1/systems',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "definitionUrl": "string",
  "id": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('//localhost:8876/v1/systems',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.post '//localhost:8876/v1/systems',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('//localhost:8876/v1/systems', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("//localhost:8876/v1/systems");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "//localhost:8876/v1/systems", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /systems`

*Create system*

Create a new system

> Body parameter

```json
{
  "definitionUrl": "string",
  "id": "string"
}
```

<h3 id="create-system-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[rest.CreateSystemRequest](#schemarest.createsystemrequest)|true|Create system|

> Example responses

> 200 Response

```json
{
  "definitionUrl": "git://github.com/foo/foo.git",
  "id": "string",
  "services": {},
  "state": "string"
}
```

<h3 id="create-system-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[v1.System](#schemav1.system)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[v1.ErrorResponse](#schemav1.errorresponse)|

<aside class="success">
This operation does not require authentication
</aside>

## delete-system

<a id="opIddelete-system"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE //localhost:8876/v1/systems/{system} \
  -H 'Accept: application/json'

```

```http
DELETE //localhost:8876/v1/systems/{system} HTTP/1.1
Host: null

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '//localhost:8876/v1/systems/{system}',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('//localhost:8876/v1/systems/{system}',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.delete '//localhost:8876/v1/systems/{system}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('//localhost:8876/v1/systems/{system}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("//localhost:8876/v1/systems/{system}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "//localhost:8876/v1/systems/{system}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /systems/{system}`

*Delete system*

Delete system

<h3 id="delete-system-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|system|path|string|true|System ID|

> Example responses

> 200 Response

```json
{}
```

<h3 id="delete-system-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[v1.Result](#schemav1.result)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[v1.ErrorResponse](#schemav1.errorresponse)|

<aside class="success">
This operation does not require authentication
</aside>

## get-system

<a id="opIdget-system"></a>

> Code samples

```shell
# You can also use wget
curl -X GET //localhost:8876/v1/systems/{system} \
  -H 'Accept: application/json'

```

```http
GET //localhost:8876/v1/systems/{system} HTTP/1.1
Host: null

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '//localhost:8876/v1/systems/{system}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('//localhost:8876/v1/systems/{system}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '//localhost:8876/v1/systems/{system}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('//localhost:8876/v1/systems/{system}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("//localhost:8876/v1/systems/{system}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "//localhost:8876/v1/systems/{system}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /systems/{system}`

*Get system*

get system

<h3 id="get-system-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|system|path|string|true|System ID|

> Example responses

> 200 Response

```json
{
  "definitionUrl": "git://github.com/foo/foo.git",
  "id": "string",
  "services": {},
  "state": "string"
}
```

<h3 id="get-system-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[v1.System](#schemav1.system)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[v1.ErrorResponse](#schemav1.errorresponse)|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="Lattice-API-Docs-teardowns">teardowns</h1>

## list-teardowns

<a id="opIdlist-teardowns"></a>

> Code samples

```shell
# You can also use wget
curl -X GET //localhost:8876/v1/systems/{system}/teardowns \
  -H 'Accept: application/json'

```

```http
GET //localhost:8876/v1/systems/{system}/teardowns HTTP/1.1
Host: null

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '//localhost:8876/v1/systems/{system}/teardowns',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('//localhost:8876/v1/systems/{system}/teardowns',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '//localhost:8876/v1/systems/{system}/teardowns',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('//localhost:8876/v1/systems/{system}/teardowns', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("//localhost:8876/v1/systems/{system}/teardowns");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "//localhost:8876/v1/systems/{system}/teardowns", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /systems/{system}/teardowns`

*Lists teardowns*

list teardowns

<h3 id="list-teardowns-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|system|path|string|true|System ID|

> Example responses

> 200 Response

```json
[
  {
    "id": "string",
    "state": "string"
  }
]
```

<h3 id="list-teardowns-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|

<h3 id="list-teardowns-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[v1.Teardown](#schemav1.teardown)]|false|none|none|
|» id|string|false|none|ID|
|» state|string|false|none|State|

<aside class="success">
This operation does not require authentication
</aside>

## teardown-system

<a id="opIdteardown-system"></a>

> Code samples

```shell
# You can also use wget
curl -X POST //localhost:8876/v1/systems/{system}/teardowns \
  -H 'Accept: application/json'

```

```http
POST //localhost:8876/v1/systems/{system}/teardowns HTTP/1.1
Host: null

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '//localhost:8876/v1/systems/{system}/teardowns',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('//localhost:8876/v1/systems/{system}/teardowns',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.post '//localhost:8876/v1/systems/{system}/teardowns',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('//localhost:8876/v1/systems/{system}/teardowns', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("//localhost:8876/v1/systems/{system}/teardowns");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "//localhost:8876/v1/systems/{system}/teardowns", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /systems/{system}/teardowns`

*Teardown system*

teardown system

<h3 id="teardown-system-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|system|path|string|true|System ID|

> Example responses

> 200 Response

```json
{
  "id": "string",
  "state": "string"
}
```

<h3 id="teardown-system-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[v1.Teardown](#schemav1.teardown)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[v1.ErrorResponse](#schemav1.errorresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[v1.ErrorResponse](#schemav1.errorresponse)|

<aside class="success">
This operation does not require authentication
</aside>

## get-teardown

<a id="opIdget-teardown"></a>

> Code samples

```shell
# You can also use wget
curl -X GET //localhost:8876/v1/systems/{system}/teardowns/{id} \
  -H 'Accept: application/json'

```

```http
GET //localhost:8876/v1/systems/{system}/teardowns/{id} HTTP/1.1
Host: null

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '//localhost:8876/v1/systems/{system}/teardowns/{id}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('//localhost:8876/v1/systems/{system}/teardowns/{id}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '//localhost:8876/v1/systems/{system}/teardowns/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('//localhost:8876/v1/systems/{system}/teardowns/{id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("//localhost:8876/v1/systems/{system}/teardowns/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "//localhost:8876/v1/systems/{system}/teardowns/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /systems/{system}/teardowns/{id}`

*Get teardown*

get teardown

<h3 id="get-teardown-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|system|path|string|true|System ID|
|id|path|string|true|Teardown ID|

> Example responses

> 200 Response

```json
{
  "id": "string",
  "state": "string"
}
```

<h3 id="get-teardown-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[v1.Teardown](#schemav1.teardown)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[v1.ErrorResponse](#schemav1.errorresponse)|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="Lattice-API-Docs-versions">versions</h1>

## list-system-versions

<a id="opIdlist-system-versions"></a>

> Code samples

```shell
# You can also use wget
curl -X GET //localhost:8876/v1/systems/{system}/versions \
  -H 'Accept: application/json'

```

```http
GET //localhost:8876/v1/systems/{system}/versions HTTP/1.1
Host: null

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '//localhost:8876/v1/systems/{system}/versions',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('//localhost:8876/v1/systems/{system}/versions',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '//localhost:8876/v1/systems/{system}/versions',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('//localhost:8876/v1/systems/{system}/versions', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("//localhost:8876/v1/systems/{system}/versions");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "//localhost:8876/v1/systems/{system}/versions", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /systems/{system}/versions`

*Lists system versions*

list teardowns

<h3 id="list-system-versions-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|system|path|string|true|System ID|

> Example responses

> 200 Response

```json
[
  {}
]
```

<h3 id="list-system-versions-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|

<h3 id="list-system-versions-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[v1.SystemVersion](#schemav1.systemversion)]|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

# Schemas

<h2 id="tocSrest.buildrequest">rest.BuildRequest</h2>

<a id="schemarest.buildrequest"></a>

```json
{
  "version": {}
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|version|[v1.SystemVersion](#schemav1.systemversion)|false|none|none|

<h2 id="tocSrest.createsystemrequest">rest.CreateSystemRequest</h2>

<a id="schemarest.createsystemrequest"></a>

```json
{
  "definitionUrl": "string",
  "id": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|definitionUrl|string|false|none|none|
|id|string|false|none|none|

<h2 id="tocSrest.deployrequest">rest.DeployRequest</h2>

<a id="schemarest.deployrequest"></a>

```json
{
  "buildId": "string",
  "version": {}
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|buildId|string|false|none|none|
|version|[v1.SystemVersion](#schemav1.systemversion)|false|none|none|

<h2 id="tocSrest.runjobrequest">rest.RunJobRequest</h2>

<a id="schemarest.runjobrequest"></a>

```json
{
  "command": [
    "string"
  ],
  "environment": "string",
  "path": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|command|[string]|false|none|none|
|environment|string|false|none|none|
|path|string|false|none|none|

<h2 id="tocSrest.setsecretrequest">rest.SetSecretRequest</h2>

<a id="schemarest.setsecretrequest"></a>

```json
{
  "value": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|value|string|false|none|none|

<h2 id="tocSv1.build">v1.Build</h2>

<a id="schemav1.build"></a>

```json
{
  "completionTimestamp": "string",
  "id": "string",
  "services": {},
  "startTimestamp": "string",
  "state": "string",
  "version": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|completionTimestamp|string|false|none|Completion timestamp|
|id|string|false|none|ID|
|services|object|false|none|Services maps service paths (e.g. /foo/bar/buzz) to the status of the build for that service in the Build.|
|startTimestamp|string|false|none|Start timestamp|
|state|string|false|none|State|
|version|string|false|none|Version|

<h2 id="tocSv1.deploy">v1.Deploy</h2>

<a id="schemav1.deploy"></a>

```json
{
  "buildId": "string",
  "id": "string",
  "state": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|buildId|string|false|none|Build ID|
|id|string|false|none|ID|
|state|string|false|none|State|

<h2 id="tocSv1.errorresponse">v1.ErrorResponse</h2>

<a id="schemav1.errorresponse"></a>

```json
{
  "code": "string",
  "message": "status bad request"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|code|string|false|none|none|
|message|string|false|none|none|

<h2 id="tocSv1.job">v1.Job</h2>

<a id="schemav1.job"></a>

```json
{
  "completionTimestamp": "string",
  "id": "string",
  "path": "string",
  "startTimestamp": "string",
  "state": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|completionTimestamp|string|false|none|none|
|id|string|false|none|none|
|path|string|false|none|none|
|startTimestamp|string|false|none|none|
|state|string|false|none|none|

<h2 id="tocSv1.nodepool">v1.NodePool</h2>

<a id="schemav1.nodepool"></a>

```json
{
  "failure_info": {
    "message": "string",
    "time": "string"
  },
  "id": "string",
  "instanceType": "string",
  "numInstances": 0,
  "path": "string",
  "state": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|failure_info|[v1.NodePoolFailureInfo](#schemav1.nodepoolfailureinfo)|false|none|none|
|id|string|false|none|none|
|instanceType|string|false|none|FIXME: how to deal with epochs?|
|numInstances|integer|false|none|none|
|path|string|false|none|none|
|state|string|false|none|none|

<h2 id="tocSv1.nodepoolfailureinfo">v1.NodePoolFailureInfo</h2>

<a id="schemav1.nodepoolfailureinfo"></a>

```json
{
  "message": "string",
  "time": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|message|string|false|none|none|
|time|string|false|none|none|

<h2 id="tocSv1.result">v1.Result</h2>

<a id="schemav1.result"></a>

```json
{}

```

### Properties

*None*

<h2 id="tocSv1.secret">v1.Secret</h2>

<a id="schemav1.secret"></a>

```json
{
  "name": "string",
  "path": "string",
  "value": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|false|none|none|
|path|string|false|none|none|
|value|string|false|none|none|

<h2 id="tocSv1.service">v1.Service</h2>

<a id="schemav1.service"></a>

```json
{
  "availableInstances": 0,
  "failureInfo": {
    "message": "string",
    "time": "string"
  },
  "id": "string",
  "instances": [
    "string"
  ],
  "message": "string",
  "path": "string",
  "ports": {},
  "staleInstances": 0,
  "state": "string",
  "terminatingInstances": 0,
  "updatedInstances": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|availableInstances|integer|false|none|none|
|failureInfo|[v1.ServiceFailureInfo](#schemav1.servicefailureinfo)|false|none|none|
|id|string|false|none|none|
|instances|[string]|false|none|none|
|message|string|false|none|none|
|path|string|false|none|none|
|ports|object|false|none|none|
|staleInstances|integer|false|none|none|
|state|string|false|none|none|
|terminatingInstances|integer|false|none|none|
|updatedInstances|integer|false|none|none|

<h2 id="tocSv1.servicefailureinfo">v1.ServiceFailureInfo</h2>

<a id="schemav1.servicefailureinfo"></a>

```json
{
  "message": "string",
  "time": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|message|string|false|none|none|
|time|string|false|none|none|

<h2 id="tocSv1.system">v1.System</h2>

<a id="schemav1.system"></a>

```json
{
  "definitionUrl": "git://github.com/foo/foo.git",
  "id": "string",
  "services": {},
  "state": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|definitionUrl|string|false|none|git url for for where the definition lives in|
|id|string|false|none|System ID|
|services|object|false|none|map for service path and services currently running in the system|
|state|string|false|none|State. One of (pending, failed, deleting, stable, degraded, scaling, updating)|

<h2 id="tocSv1.systemversion">v1.SystemVersion</h2>

<a id="schemav1.systemversion"></a>

```json
{}

```

### Properties

*None*

<h2 id="tocSv1.teardown">v1.Teardown</h2>

<a id="schemav1.teardown"></a>

```json
{
  "id": "string",
  "state": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|false|none|ID|
|state|string|false|none|State|

