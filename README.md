# Dockerize-NodeApp
This project is to Dockerize a simple Node.js application.  It contains Package.json and Server.js

package.json- This file contains dependancies this application uses

Server.js- This file contains actual code it uses express module for setting up web based application.

This application runs on port 8080 and shows welcome text.

Pre-requisits:

	Docker must be installed 

	Need any code editor

To run the application on the docker we need a docker image.

1.Lets create Docker file

	FROM node:14

	WORKDIR /app

	COPY package*.json ./

	RUN npm install

	COPY . . 

	EXPOSE 8080

	CMD ["node","Server.js"]
	
2.Build this docker file

	 docker build -t node-app
	
3.Check images

	 docker images
	
4.Run docker image to create container

	 docker run -d -p 8080:8080 node-app
	
5.See containers running

	 docker ps
	
6.Open browser and type localhost 8080 u will see "welcome" text.

I hope this tutorial helped you get up and running a simple Node.js application on Docker container.



