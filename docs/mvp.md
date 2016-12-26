# MVP of _sammler_

## Table of Contents

- [MVP Definition](#mvp-definition)
- [Implementation Details](#implementation-details)
- [Isn't that overkill ?](#isnt-that-all-overkill)

## MVP Definition

The first MVP of *sammler* is defined as follows:

### Functionality

The following information should be fetched on a daily basis **from GitHub**

- GitHub profile
	- Who and how many followers do I have on my GitHub profile?
	- How did this changed compared to the previous day:
	  - Increase/decrease of followers  (e.g. compared to yesterday/last week/last month)
		- Who are the new followers?
		- Who did stop following me?
- GitHub repositories
	- Store the details of all *public* GitHub repositories
	- For each of the repositories:
	  - Increase/decrease of followers (e.g. compared to yesterday/last week/last month)
		- Who follows the repository?
		- Who are the new followers (compared to the previous day)?
		- Who stopped following a repository (compared to the previous day)? 



### Infrastructure Requirements

- The entire infrastructure should be able to created locally by just a `docker-compose up`.
- Follow the principles of a microservices architecture (lousily coupled services, etc.)
- Deployment to DigitalOcean should be done with only a few lines of code.
- Using a message bus from the beginning.
- Orchestrate the services as automated as possible from the beginning.
- Logging, Error Handling, etc.
- Fully configurable.
- New versions of a services should be deployable with zero manual efforts.



## Implementation Details

A few building blocks will have to be created to get to the MVP:

Some implementation details so far:

- As I have chosen PostgreSql for the first service, I had to create a REST wrapper for flywaydb.org to migrate new versions of the data-structure fully automated.
- Chosen RabbitMq as a message bus.
- To schedule the sync work, scheduled messages need to be sent to RabbitMQ, create a very rudimentary node.js service doing that.
- Started to use consul to orchestrate the services.

See [Checkpoint #1](mvp-cp-1.md)


## Isn't that all overkill?

Yes, it is ;-)  
The MVP can probably achieved just with a few lines of code, collecting some data from GitHub and comparing it with some stored data. But that's not the point.  
Instead I am trying to build an infrastructure and code-base with the MVP, which can then be used to extend the service and to easily add other services on top of the infastructure.  
Beside that - and that's another goal of this project - I am constantly learning new technologies and want to understand in detail what the real challenges are when creating a microservices based solution and operating it on a daily basis.