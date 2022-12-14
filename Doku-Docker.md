---
title: Docker Tasks Doku
description: 
published: true
date: 2022-11-13T19:37:35.940Z
tags: 
editor: markdown
dateCreated: 2022-11-13T19:07:02.731Z
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

ADD ./helloworld /bin/hw

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

### refresh einbauen und ENTRYPOINT nutzen

-   `nano dockerfile`:

```docker
FROM ubuntu

RUN apt-get update && apt-get install -y curl

ENTRYPOINT ["sh", "-c", "while true; do clear && curl wttr.in; sleep 5; done"]
```

-   `docker build -t weather .`
    
-   `docker run --rm --name weather -dit weather`

### Healthcheck

- `nano dockerfile`:

```docker
FROM ubuntu

RUN apt-get update && apt-get install -y curl

HEALTHCHECK CMD curl --fail http://wttr.in/ || exit 1

CMD ["sh", "-c", "while true; do clear && curl wttr.in; sleep 5; done"]

```
- `docker build . -t weather`

- `docker run --rm --name weather -dit weather`
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

  weather.find({search: "Landshut,DE", degreeType: 'C'}, function(err, result){
   if(err){
    console.log(err);

    res.status(500);
    res.send("internal Err");
    return;
   }

   console.log(JSON.stringify(result, null, 2));
   res.json(result);

  });
  
});

app.get('/:location', (req, res) => {

  weather.find({search: req.params.location, degreeType: 'C'}, function(err, result){
   if(err){
    console.log(err);

    res.status(500);
    res.send("internal Err");
    return;
   }

   console.log(JSON.stringify(result, null, 2));
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

### Healthcheck

```docker
FROM node

WORKDIR /usr/src/app

RUN npm install weather-js express

COPY ./server.js .

EXPOSE 8080

HEALTHCHECK CMD curl --fail http://localhost:8080 || exit 1

CMD ["node", "server.js"]
```
