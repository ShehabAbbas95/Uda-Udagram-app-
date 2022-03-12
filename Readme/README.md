# Hosting a full-stack application 

## Overview
This project aims  to deploy a web app on AWS using CircleCI, Elasticbeanstalk, S3 Bucket and Postgres RDS  from Amazon Web Services.

### Instructions
### 1. The steps to install the app and packages
- install Nodejs@v14.16.0 from `https://nodejs.org/download/release/v14.16.0/`
- check npm version, I'd used npm@6.12.0
    ### Install API Endpoint
    1. Go to backend folder i.e `cd backend` in your terminal
    2. Npm i then npm run build and it will build the api server to run the server locally 
    3. make sure you are connected to the DB and provide your database credentials into a .env file don't forget 
    to add it to .gitignore file.
    4. Follow the link `http://Backend-env.eba-wj3uppk8.us-east-1.elasticbeanstalk.com/api/v0/feed:8080` to view the api end point
    ### Install front-end
    1. Go to udagram-frontend folder i.e (cd udagram-frontend) in your terminal
    2. Npm i then npm run build and it will build the frontend app.
    3. Follow the link `http://http://sheboudagram.s3-website.us-east-2.amazonaws.com/home` to view the app

    
