# SOON_ FM 2.0 Tehcnical Specification 

The technical details of how SOON_ FM 2.0 can work, moving to a move evented, microserviced architecture.

**This is very much a work in progress and likely to change as systems are fleshed out.**

## Tehcnical Overview

The main characteristics of SOON_ FM 2.0 are:

* A microserviced architecture: Concerns are limited to specific context boundaries, with 1 or more services operating in that boundary. For example, a Queue Boundary, services responsible for managing the Queue. This also makes it easier for new services and features to be added.

* Less HTTP, more Async: HTTP has a heavy overhead, moving to a message queue based asynchronous system will allow us to remove a lot of the HTTP overhead on our REST API's, where appropriate ofcourse. Services which care about specific events can subscribe to specific events via Pub/Sub style system and act accordingly as required. For example a Stats service can subscribe to track play events, when an event is fired it can then process that event asynchronously.
