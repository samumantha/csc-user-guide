# Notebooks Concepts

This document defines terminologies in notebooks service.

## Notebooks aka Notebooks.csc.fi

- CSC service for interactive web based applications

## Environment template

- Created by Admin
- Tied to a Cluster
- Has attributes needed by Cluster
- Has attributes selected for customization per Environment.
- Templates define the images and configurations.
- Available images are [notebooks-image](https://github.com/CSCfi/notebook-images/tree/master/builds) 

## Environment

- Predefined content for one learning session
- Usually a Docker container - either JupyterLab or RStudio
- Created by Workspace manager based on Environment template

## EnvironmentSession

- One running copy of an Environment
- Owned by user
- Has lifetime set by Environment

## Workspace

- A collection of Environments and Users.
- Has an owner
- May have managers
- Has a lifetime
- May contain shared [Persistent](persistentdata.md) Workspace data
- May contain Persistent User data

## Persistent user data

- A persistent directory, storing data between environment session launches
- Available in the environment session in a directory configured by Workspace manager
- Is tied to a workspace
- Has lifetime tied to a Workspace

## Workspace data

- Shared data directory available to all users in a Workspace
- Is writable by Workspace manager
- Is tied to a workspace
- Has lifetime tied to a Workspace

## Join code

- Unique Code generated for each workspace
- Workspace owner distributes this code for users to join the workspace

## End user

- A workspace participant or a user of public Environments
- Is authenticated
- May launch environment sessions
- Has access to public Environments
- May be part of Workspaces
- Has access to Workspace Environments through membership

## Workspace owner

- Principal of the Workspace
- Creates workspace and the contents for their users.
- May add managers
- Acts as a manager

## Workspace manager (Assistant?)

- Can create contents in the workspace
- May add users
- May add Environments based on Environments templates

## Admin

- System administrator
- Has full rights in the system

## Cluster

- A resource for executing the environment sessions
- In practice: some sort of Kubernetes cluster
- Configured by Admin

