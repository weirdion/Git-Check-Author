Git-Replace-Author
===================
P532 - Sub-Project : Git hooks written in bash, to filter Author Name/Email used.
----------

Hooks
-------------
*pre-receive* : This hook is triggered after a local commit is pused.
This hook checks the Author Email against authorized_keys, and then Author Name against Author Email to enforce a standard format of committing.

*pre-commit* : This hook is triggered before a local commit is made.
This hook checks the Author Name against the Author Email to enforce a standard format of committing.
>*Note*: This is a client-side hook, which means it won't be copied when someone clones a repository. Therefore, this is not ideal to be used to enforce the Author Name pattern.

Observations
-------------

1. Both Author Name and Author Email are used by Bamboo. So both need to be checked to avoid duplicate profiles.
2. Only Author Email is used by SonarQube's SCM. So only Author Email needs to be checked to prevent random profiles.
3. Committer Name/Email isn't used in Bamboo or SonarQube, so there's no need to test it.
