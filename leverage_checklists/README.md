# Leverage Checklists

- Being an effective software architect it is highly important to get checklists in place for most of the processes.
- Effective checklists are the ones where it is known which process is to be included and which one is to be parked outside.
- The processes that are found to have a procedural flow of dependent tasks doesn't require checklists.
- Also, the process that are extremely simple and can be executed without error also doesn't require checklists.
- Example: Process to create database tables. These are just series of steps. They are not qualified to be checklist.

| done    | task description                                  |
|---------|---------------------------------------------------|
| &#9745; | Determine database field names and types          |
| &#9744; | Fill out database request forms                   |
| &#9744; | Obtain permission for new database table creation |
| &#9744; | Verify database table once created                |


- Those processes that are error-prone or may have steps that are subject to be skipped frequently are qualified to have a checklist.
- These processes are non-dependent tasks that doesn't follow procedural order.
- Example: Source code completion or code review checklist.

| done    | task description                                    |
|---------|-----------------------------------------------------|
| &#9745; | Coding standard and formatting using standard tools |
| &#9744; | Frequently overlooked items                         |
| &#9744; | Application specific standards                      |
| &#9744; | Special team or project instructions                |

- Example: Code release and deployment checklist

| done    | task description                                |
|---------|-------------------------------------------------|
| &#9745; | Associated config changes & server config files |
| &#9744; | Additional 3rd party libraries (Jar, DLL etc.)  |
| &#9744; | Database update and database migration script   |
| &#9744; | Specific error prone situation                  |

- It is fine to add obvious steps in checklist that may subject to get skip occasionally
- Try to keep checklist as compact as possible
- As a software architect don't create checklist by yourself. Create a democratic process and involve Development teams to achieve it. Collaborate with development team.
- Don't go overboard and add every process 
