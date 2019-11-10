This Redmine stack is intended to execute on a docker Swarm cluster. The
installed docker version must be be 18.09.5 or newer. Older versions do not support
docker Swarm and will not recognize the version of the yml files in this
project.

Before deploying for the first time, download the PurpleMine2 theme zipfile
and expand it in this directory. This will create a directory named
PurpleMine2-master which is needed at execution time.
```
$ wget https://github.com/mrliptontea/PurpleMine2/archive/master.zip && unzip master.zip && rm master.zip
```

The stack uses two docker volumes to ensure data is persisted between executions.
The Postgres data is in volume redmine-pg-data. Any Redmine files are in the
volume redmine-files.
