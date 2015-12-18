# Sentinel

Sentinel is aimed to be a centralized and distributed self-hosted system monitor software for monitoring _expirable_ resources with predictability capabilities and asynchronous alerting mechanisms.

For example assuming we want to monitor **Disk Space Usage**:

* It will estimate when it would reach the maximum limit, based on previous recorded metrics, and
* It will alert different channels when criteria applies, for example **> 80% Disk Usage**

Something along the lines of:

> At this rate your Disk Usage will reach 100% in Two Days; alerting on Slack Channel #alert

## Architecture

*Sentinel* will consist of multiple *nodes* that will notify a central *server* their status periodically.

### Nodes

**Node** is a computer system part of a network (virtual or physical) that is being monitored. The *node* will periodically notify the *server* its status. This is the distributed element of *Sentinel*. [0MQ](http://zeromq.org/bindings:go) will be used for communicating *nodes* and *server*.

### Server

**Server* is the centralized element in *Sentinel*. It is in charge of saving all the information received by the *Nodes*. It will be using [MongoDB](https://docs.mongodb.org/ecosystem/drivers/go/) for storing information comming from the *nodes*.

## Initial Scope

### Monitorable Resources

* CPU
* Disk Usage
* Memory

### Channels

* Email
* Slack
