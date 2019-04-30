# Create docker file:

  ## Steps to create a docker file
    vim dockerfile    ==> Create a new docker file...
    
    File contents:  
        FROM node:7
        WORKDIR /app
        COPY package.json /app
        RUN npm install
        COPY . /app
        CMD node index.js
        EXPOSE 8081

