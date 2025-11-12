# mop

Manage and organise projects. CLI tool that allows a team to plan, organise and manage work remotely. Users can create projects, designate goals and divide them into tasks. Different team members can be assigned to tasks, provide feedback into their work and update their status. mop also works with blocks in mind. A task can block another, meaning that until one task is not finished, the other cannot be done.

Another core feature of mop is its privilege system, where users can only perform actions that are allowed to do. Privileges types varies from viewing to working and some others. They are also hierarchical, meaning that privileges are passed down from projects to goals and from goals to tasks. This allows mop workflow to adapt to different team organisations. For further details check our [Documentation](doc/GENERAL.md).

mop is **currently in development**, which means that everything previously stated is subjected to be implemented and changed.

# Technical details

This piece of software is meant to be a project for personal use and learning purposes. Also, the goal is to create a piece of software that is well designed, documented and efficient. For all these reasons, the project will be entirely made in C and will require as minimum dependencies as possible.

# Roadmap

In order to plan the development, we are expecting to bring features iteratively in each version, which we describe below.

## V0.1

First prototype of the software. Can initialize an instance and work locally with it. Can create projects, goals and tasks. Can modify their status and tags. Can set task as block for another.

## V0.2

Remote features. Instance can be accessed from other machines/network. Users can join the instance and interact with it remotely.

## V0.3

Privileges system. Every user can be granted different types of privileges and their actions are restricted based on those they have.

