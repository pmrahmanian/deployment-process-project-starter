# Udagram FullStack Infrastructure

## Diagram
![Udagram Infrastructure Diagram](./Architecture.png?raw=true "Udagram Infrastructure Diagram")

## Overview

This app is fully hosted on AWS. End users access our app via our Udagram-Frontend [Angular](https://angular.io/) built front end hosted on an Amazon S3 Bucket.

Lifecycle and User events trigger api **Requests** sent to our Udagram-API [Node](https://nodejs.org) / [Express](https://expressjs.com/) server hosted on Amazon Elastic Beanstalk. 

This server processes requests and interacts with our postgreSQL database to persist data. This postgreSQL database is hosted on an Amazon RDS instance and has a Users and FeedItems tables.

The API server formats and sends **Response** objects back to the frontend application.
