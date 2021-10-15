# Csc Notebooks

[Csc Notebooks](https://notebooks-beta.rahtiapp.fi) provides dedicated and disposable environments run in the csc cloud and can be accessed through web browser.

## Concepts

* [Terminologies](terminologies.md)

## How to access notebooks.csc.fi ?

Csc Notebooks can be accessed using one of the options haka, virtu or csc-customer.

Check if your institution belogs to haka or virtu here :

* [Haka institutions](https://wiki.eduuni.fi/pages/viewpage.action?pageId=27297776)
* [Virtu institutions](https://wiki.eduuni.fi/display/CSCVIRTU/Organisaatiot)

## How to use notebooks.csc.fi ?

1. Self -learning
2. Host courses
3. Collaborations among teams

### Self-learning users:

1. After logging in, the environments page has few environments possibly contents for learning. When you launch these environments, they spawn an environment session in csc cloud.
3. When you are finished learning, destroy the environment sessions. 
4. The running environment session is destroyed automatically when the lifetime of pod is reached.

### Host courses:

1. Login to Csc notebooks
2. Send an email to <servicedesk@csc.fi> requesting workspace owner rights
3. Once the access is given, go to "manage workspaces" and click "create workspace"to create a workspace.
4. Create an environment through "Environment creation wizard" or "use simple editor". Provide the following configurations:

```
Environment template: Select the template depending on the [image] (https://github.com/CSCfi/notebook-images/tree/master/builds) needed. 

Environment name(required): Give a valid meaningful name.

Environment description(required): Provide a detailed description to helps users to understand more about the environment.

Labels(optional): Select the default labels or create custom labels. Labels are useful in searching environments.

Interface: Jupyterlab or jupyter Notebooks. Applicable only for jupyter based environments.

Download Method: The location to download the course contents from. Choose 'git clone' if you wish to download from git repository or choose 'Download from url' if you have contents hosted in [allas](http://docs.csc.fi/data/Allas/) or elsewhere and provide the url.
```

!!! note
    The external location should be publicly accessible. For example git 
    repos should be public repositories.

As an alternative, the course contents can be uploaded in 'shared-data' folder and users in the workspace can directly read from that.


## Security guidelines for Workspace owners:

- Do not store sensitive data or data sets. 
- Share join code only with users you wish to join your workspace
- If you are creating custom images for your course, do not store any keys or sensitive data in the image. 
- Delete the workspace as soon as the course is over.

### References

* [Poject jupyter homepage](https://jupyter.org/)
* [Project rstudio homepage](https://www.r-project.org/)
* [CSC rahti container cloud](https://docs.csc.fi/cloud/rahti/)
* [CSC IaaS cloud service](https://docs.csc.fi/cloud/pouta/)



