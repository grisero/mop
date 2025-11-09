# mop
Manage and organise projects. CLI tool for collaborative projects.

Currently in design phase.

# Introduction

mop needs a machine to be hosted, where all the information will be stored. It can be local (for individual projects, preferably) or in a server that will listen permanently and work through a daemon.

It all starts with an **instance** created in the host machine.

```
mop init name_of_instance
```

Once initiated, the owner of the instance becomes the administrator. An instance can host one or several **projects**. Each project can set **goals** and each goals can be divided in **tasks**. It is up to the users to define the complexity and granularity of goals and tasks.

Every goal and task has a **status** associated with it. The next status come predefined:

- **planned**: Initial status. It is planned to be made in the future.
- **working**: The team started working on it.
- **blocked**: Cannot continue due to another task/goal blocking its progress.
- **approving**: It is awaiting for approval.
- **achieved**: Goal has been approved and therefore achieved.

Also, goals and tasks can have **tags** to classify them. These are useful for privileges purposes (see [Users](#Users)).

As in every project, **blocks** are a part of mop workflow. We can define **requires** as every goal or task that must be done in order to be able to work in a specific goal/task. If every achievable task in a goal has been achieved and there are only blocked tasks left, goal is set automatically as blocked.

# Users

Any user can join an instance using the **join** command:

```
mop join username@host_ip:name_of_instance
```

A request will be send to the administrators of the instance who will accept or decline the join request. If they accept, administrator can also grant certain **privileges** to the user. All privileges that can be granted are listed below:

- **view**: Able to view all info and progress.
- **plan**: Can create goals or tasks. Can set tags.
- **work**: Can be assigned to goals or tasks to work on them.
- **approve**: Can approve goals or tasks.
- **grant**: Can grant privileges to another user

Privileges are **hierarchical**. A user with certain privileges on an instance will have the same on all of its goals and tasks. A user with privileges on a goal will also have privileges on all its tasks. Tasks are the lowest level in the hierarchy. The **grant** privilege works hierarchically too, so a user can only grant privileges at a lower level than theirs.

Privileges are also **tag based**. We can define privileges of a user based only on certain tags. For example, we can define the tag _development_ and apply it to several projects. Then, we can set set a user's privilege based on tag _development_, so that he only have those privileges on projects tagged as _development_. Same can be apply to any level on the hierarchy.

```
mop grant [USERNAME] [PRIVILEGE] [SCOPE]
```

The **scope** of a privilege tells the level in the hierarchy and its potential tags. An example of a grant command that gives privileges to a user named '_Bob_' in an instance named 'Foo' to work on every project tagged as _development_ or _testing_:

```
mop grant Bob work Foo.[development|testing]
```
