# Persistence storage:

Types of persistent storage

* Persistence for session lifetime(home)
* Persistence for workspace(shared-data)
* Persistence per user per workspace(work)

!!! note
    'home' folder refers to 'home/jovyan' for jupyter based environments
    and '/home/rstudio' for rstudio based environments.

## Persistence for session lifetime:

* This is the default persistence provided for the sessions. The data is preserved when the container restarts in the middle of running session. A volume is created and mounted on /home/(jovyan/rstudio) when the session is launched.
* This is the default folder for the user.
* The volume is deleted when the session is deleted by user or when the lifetime of session expires. 
       
## Persistence for workspace:

* A shared volume is created by the workspace-owner for his workspace. This volume is mounted in /home/(jovyan/rstudio)/shared-data for each sessions launched. Every user in the workspace will have read access to this folder. 
* The default size of the volume is 20GB.
* Workspace-owner and workspace-manager will have write access to this volume. Other users in the workspace has read access.  
* Shared-data is directly linked to the lifetime of workspace. When the workspace is deleted, shared folder will be automatically deleted

### Tips to use: 
    Workspace-owner/manager can create, modify and save course contents in the shared-data folder and the other users can directly read from them. 


## Persistence per user per workspace:

* By default this volume is not available. Workspace-owner can decide if he wants the users in his workspace to have this volume when creating the environment.
* If enabled, a volume will be created for the user in his workspace when he launches the session for the first time. Other users or workspace owners in the workspace will not have any access to the individual users volume.  
* This volume is mounted in /home/(jovyan/rstudio)/work. 
* The default volume size is 1GB.
* The volume is peristed even if the session is destroyed in the workspace. Volume is destroyed only when the workspace expires.

### Tips to use: 

Individual users can store and save their course data in this volume until the end of the workspace lifetime. Unlike session volume, this is not deleted when the session expires. Users can launch new session again in the workspace and this volume data still exists. 

