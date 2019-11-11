This Redmine stack is intended to execute on a docker Swarm cluster. The
installed docker version must be be 18.09.5 or newer. Older versions do not 
support docker Swarm and will not recognize the version of the yml files in 
this project.

Before deploying for the first time, download the PurpleMine2 theme zipfile
and expand it in this directory. This will create a directory named
PurpleMine2-master which is needed at execution time.
```
$ wget https://github.com/mrliptontea/PurpleMine2/archive/master.zip && unzip master.zip && rm master.zip
```

The stack uses two docker volumes to ensure data is persisted between 
executions. The Postgres data is in volume redmine-pg-data. Any Redmine files 
are in the volume redmine-files.

The stack relies on environment variables. redmine-environment provides an
example of how the variables can be set. It is suggested that this file be copied 
to redmine-environment.prod as that file will be ignored by this git repo, so 
your production values will be less likely to find their way back here.

It is acknowleged that docker secrets provide a secure alternative to
environment variables but the tradeoff for convenience is acceptable for
this repo given its low-value as a target and the plan for remote daily backups 
of the data.
