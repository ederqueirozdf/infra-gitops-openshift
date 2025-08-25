 # Disabling Self-provisioning

 You can prevent an authenticated user group from self-provisioning new projects.

    Log in as a user with cluster-admin privileges.

    Remove the self-provisionerscluster role from the group.

    $ oc adm policy remove-cluster-role-from-group self-provisioner system:authenticated system:authenticated:oauth

Set the projectRequestMessage parameter value in the master-config.yaml file to instruct developers how to request a new project. This parameter value is a string that will be presented to a user in the web console and command line when the user attempts to self-provision a project. You might use one of the following messages:

    To request a project, contact your system administrator at projectname@example.com.
    To request a new project, fill out the project request form located at https://internal.example.com/openshift-project-request. 

Example YAML file

...
projectConfig:
  ProjectRequestMessage: "message"
  ...

