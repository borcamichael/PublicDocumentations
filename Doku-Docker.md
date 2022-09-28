---
title: Docker Tasks Doku
description: 
published: true
date: 2022-09-27T18:41:12.959Z
tags: 
editor: markdown
dateCreated: 2022-09-27T15:32:27.479Z
---

# Docker Image from Scratch - HelloWorld with golang

## For Ubuntu:

-   Install golang: `sudo apt-get update && sudo apt-get install golang`
-   `nano helloworld.go` :

```go
package main

import "fmt"

func main() {
   fmt.Println("Hello, World!")
}
```

-   `go build helloworld.go`
-   `nano dockerfile`:

```docker
FROM scratch

ADD ./hw /bin/hw

CMD ["/bin/hw"]
```

-   `docker build -t helloworld .`
-   `docker run -it --rm helloworld`

# Docker Image für Container der Wetterlage ausgibt

## Mit Ubuntu:

-   `nano dockerfile`:

```docker
FROM ubuntu

RUN apt-get update && apt-get install -y curl

CMD ["curl", "wttr.in"]
```

-   `docker build -t weather .`
-   `docker run -it --rm weather`

## Mit NodeJS:

-   `nano server.js:`

```javascript
var weather = require('weather-js');

// Options:
// search:     location name or zipcode
// degreeType: F or C


const express = require('express');

// Constants
const PORT = 8080;
const HOST = '0.0.0.0';

// App
const app = express();
app.get('/', (req, res) => {

  weather.find({search: 'Landshut, DE', degreeType: 'C'}, function(err, result){

   if(err) console.log(err);
   res.json(result);

  });

});

app.listen(PORT, HOST);
console.log(`Running on http://${HOST}:${PORT}`);
```

-   `nano dockerfile`:

```docker
FROM node

WORKDIR /usr/src/app

RUN npm install weather-js express

COPY ./server.js .

EXPOSE 8080

CMD [ "node", "server.js" ]
```

-   `docker build -t weatherjs .`
-   `docker run -p 8080:8080 -dit --rm weatherjs`