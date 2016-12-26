# MVP - Checkpoint #1

Purpose: Verify the concept of long running tasks.   
Demonstrate and test how RabbitMQ works best and in the most efficient way to run several tasks and reports their status.

## Components

- **s5r-rabbitmq** - RabbitMQ [pre-configured](https://github.com/sammler/sammler-rabbitmq)
- **s5r-log-service** - A simple [logging service](https://github.com/sammler/sammler-log-service)
- **s5r-jobs-service** - A simple [job (tracking) service](https://github.com/sammler/sammler-jobs-service)
- **s5r-scheduler** - A simple job scheduler

## Basic Flow

Purpose of the job `github.profile.sync`:

- Sync the profile  
- Sync the profile-history  
    - followers by day  
    - stargazers by day  
    - repos  

---

Independently from the flow:

- The `s5r-scheduler-service` posts jobs to s5r-rabbit-mq
- At the same time the jobs are saved to `s5r-jobs-service` using a unique id, which is also used in the RabbitMQ message
- RabbitMQ is set up as follows:
    - foo
    - bar 
    - baz

---

The flow:

- `s5r-strategy-github` queries for messages in `s5r-rabbitmq` matching `github.profile.sync`
- On retrieving job `github.profile.sync` (logic all handled in `s5r-strategy-github`):
    - Job is marked as `running` in `s5r-jobs-service`
    - Job `sync` starts on `s5r-strategy-github`
    - GitHub profile
        - gets retrieved from GitHub APIs and 
        - stored to `s5r-db`
        - logged to `s5r-log-service`
    - Sub jobs are created (on `s5r-rabbitmq` and `s5r-jobs-service`):
        - `github.followers.sync`
        - `github.stargazers.sync`
        - `github.repos.sync`
    - `github.profile.sync` gets acknowledged on `s5r-rabbitmq` (using the job id)

## Questions to answer & verify

- What's the best way to run multiple job in a reliable way async