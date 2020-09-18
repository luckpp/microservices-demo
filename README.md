# microservices-demo

This is a very basic implementation of a simple **microservices architecture**.

The technologies that will be used:
- Node.js
- Docker
- Kubernetes
- Skaffold


## Lessons to learn from the current project

### 1. Data Handling

- this is a big challenge in a microservices architecture
- it gets more complex as the data model is larger

### 2. Sharing data between services

- there is more than way of sharing data between services:
  - **sync communication**: when one services call directly the API of another service
  - **async communication**: focuses on communicating changes using **events** sent to an **event bus** (the preferred method)
  - combination between sync and async communication

### 3. Async communication

- as previously noted, the async communication involves the use of an **event bus**
- it is up to the **event bus** to delivering the events to all interested **services** inside of our application
- the **services** can react to events
- with this communication method, every **service** ends up being self-sufficient 
  - if any other service fails, we can have the rest of our application work, since there are no strict dependencies between services

### 4. Docker

- Docker makes it easy to package up services

### 5. Kubernetes

- Kubernetes is a container orchestrator
- it is a pain to do the setup
- makes really easy to deploy & scale services


## Issues with the current project

- duplicate code
- really hard to picture the flow of events
- really hard to remember what properties an event should have
- really hard to test the event flows
- the machine that runs Kubernetes and Skaffold might get slow
- if we emit very quickly a series of events we might break our data model
  - maybe events will end up flow in our application *out-of-order*
