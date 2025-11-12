# Persistent data

This file describes what, where and how mop stores information.

## What

In order to function, mop needs to have stored:

- Every instance in the machine. An instance represents an entity, team or organization that work together. There can be none or multiple instances in the same machine. 
    - Name of the instance
    - Hash ID
- Every project in an instance. Represents something that the team wants to work in. Projects are not design to finish. They can be active infinitely so we can treat them as departments or sub-teams.
    - Name of the project
    - Hash ID
    - Tags
- Every goal in a project. Represents something that the team wants to see come true. Something they want to achieve. Goals can be think of as milestones, big checkpoints in a team big picture's job.
    - Name of the goal
    - Hash ID
    - Tags
    - Status
- Every task in a goal. Tasks appear when we divide a goal into simpler and smaller steps. Tasks are actions with tangible results that team members can work in directly.
    - Name of the task
    - Hash ID
    - Tags
    - Status
    - Blocked By

## Where

All this data is stored in one single file, that is located in a hidden directory in the user's home.

```
$HOME/.mop/data
```

## How

The way to store this information is a plain text file _data_. This file contains the information structured in tables, rows and fields. All these structures are separated using ASCII control characters 1D, 1E and 1F.
