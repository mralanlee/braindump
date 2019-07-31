# SWF
- Simple Workflow Service
- Webservice that makes it easy to coordinate work across distribute application components.
- Use Cases:
  - Media Processing
  - Web application back-ends
  - Business process workflows
  - Analytics pipelines
  - Designed as a coordination of tasks
- Tasks represent invocations of various processing steps performed by executable code, web service call, human actions, scripts.

#### Workers
Programs that interaction with SWF to get tasks, process received tasks, and return results

#### Decider
Program that controls coordination of tasks, i.e. ordering, concurrency, and scheduling according to the application logic


## Workers and Deciders
- Can run on cloud infracstructure or on machines behind firewalls
- SWF Brokers the interactions between workers and the decider
- Allows decider to get consistent views into the progress of tasks and initiate new tasks in an ongoing manner
- SWF stores tasks, and assigns them to workers when they are ready and monitors their progress
- Ensures a task is assigned only once and never duplicates
- Maintains app state durably, workers and deciders dont' have to keep track of execution state
- Run independently and scale quickly

### Main Differences Between SWF and SQS
- Tasks are only assigned once and never duplicated.
- SWF is task oriented, SQS is message oriented
- SWF keeps track of all tasks and events in an app, SQS requires you to track in-app state

## Domains
- Workflow and activity types and the work execution itself is all scoped to a domain
- Domains isolate a set of types, executions and task lits from others within the same account
- Register a domain by using AWS management console or by using RegisterDomain action in Amazon SWF API

Parameters are specified in JSON by key values of `name`, `description`, `workflowExecutionRetentionPeriodInDays`

Maximum workflow can be 1 year, and values are measured in second

## SWF Actors
- Workflow starters: An application that can initiate or start a workflow
- Deciders: Control the flow of activity tasks in a workflow execution. Decider decides what to do next.
- Activity Workers: carry out activity tasks
 
