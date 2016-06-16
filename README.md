# SOON_ FM 2.0 Technical Specification 

The technical details of how SOON_ FM 2.0 can work, moving to a move evented, microserviced architecture.

**This is very much a work in progress and likely to change as systems are fleshed out.**

## Tehcnical Overview

The main characteristics of SOON_ FM 2.0 are:

* A microserviced architecture: Concerns are limited to specific context boundaries, with 1 or more services operating in that boundary. For example, a Queue Boundary, services responsible for managing the Queue. This also makes it easier for new services and features to be added.

* Less HTTP, more Async: HTTP has a heavy overhead, moving to a message queue based asynchronous system will allow us to remove a lot of the HTTP overhead on our REST API's, where appropriate ofcourse. Services which care about specific events can subscribe to specific events via Pub/Sub style system and act accordingly as required. For example a Stats service can subscribe to track play events, when an event is fired it can then process that event asynchronously.

## Core Features of SFM_ 2.0

* Add / Delete (your own) items from the Queue
* Voting mechanic to move tracks down or up or even off the Queue.
* Points based DJ of the week (up for discussion):
  * 1 Point for adding a track to the Queue (Who upvoted is listed in the track)
  * 1 Point per track upvote (1 per user)
  * 3 Points for a track moving up the top of the Queue
  * -1 Point for removing your own track from the Queue
  * -1 Point for a track being skipped during play (the skipper will be named and shamed)
  * -3 Points for a track falling off the Queue (Who down voted is listed in the track)
* Track reactions? (Slack Style)
* Google Authentication (thisissoon.com/thishe.re)
* New imroved statistics system
* Pause Tracks
* Skip Tracks
* Mute
* Adjust Volume +/-

## Ideas (please add your own)

* Playlist crafter - Build a playlist and add that in one go
* Support for other streaming services (e.g SoundCloud - API's dependant)
