# Implementation

## Step 1: Analyze the Monolithic Application

The original application was hosted on the `MonolithicAppServer` EC2 instance.

The application was a Node.js monolith where the web interface, administration functionality and business logic operated on the same server.

## Step 2: Decompose the Application

The monolith was divided into two services:

### Customer Service

Responsible for supplier catalog browsing.

### Employee Service

Responsible for supplier management and CRUD operations.

Administrative functionality uses the `/admin/*` route prefix.

## Step 3: Containerization

The services were packaged as Docker containers using Node.js Alpine images.

The containers were tested for:

- Application functionality
- Database connectivity
- CRUD operations
- Data persistence
- Port configuration

## Step 4: Amazon ECR

Two private Amazon ECR repositories were created:

```text
customer
employee
