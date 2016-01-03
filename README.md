# Sentinel

Sentinel is aimed to be a centralized/distributed self-hosted system monitor software for monitoring _expirable_ resources with predictability capabilities and asynchronous alerting mechanisms.

For example assuming we want to monitor **Disk Space Usage**:

* It will estimate when it would reach the maximum limit, based on previous recorded metrics, and
* It will alert different channels when certain criteria applies, for example **> 80% Disk Usage Reached**

A practical example would be something along the lines of:

> Estimation: At this rate your Disk Usage will reach 100% in Two Days.

> Alert: Slack Channel #alert

## Architecture

*Sentinel* will consist of multiple *nodes* that will notify a central *server* their status periodically.

### Nodes

**Node** is a computer system part of a network (virtual or physical) that is being monitored. The *node* will periodically notify the *server* its status. This is the distributed element of *Sentinel*. [0MQ](http://zeromq.org/bindings:go) will be used for communicating *nodes* and *server*.

### Server

**Server** is the centralized element in *Sentinel*. It is in charge of saving all the information received by the *Nodes*. It will be using [MongoDB](https://docs.mongodb.org/ecosystem/drivers/go/) for storing information coming from the *nodes*.

## Initial Scope

### Monitorable Resources

* Disk Usage
* Memory

### Channels

* Email
* Slack

# Disclaimer

This is my attempt to make something meaningful while learning three *new* things:

1. Programming language: Go,
2. Messaging Library: ZeroMQ, and
3. NoSQL database: MongoDB

so **do not** expect anything to be stable or production ready, unless **I say so**.
