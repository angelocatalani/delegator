# Delegator

The Delegator is a web application to execute commands to pre-configured servers through SSH.

The command output is fecthed asynchronously until the task completes.

To read asynchrously the command's standard output and standard error, 
they are redirected respectively to the target server local files: <task-id>.stdout and <task-id>.stderr.

When the command completes, the most recent portion of the output is stored in the database.

The SSH connection to the target server is closed as soon as the commands are executed without waiting for termination.

## Backed API

`POST /task`: run the command to the target server

`GET /task/status/<task-id>`: returns the task status together with its most recent portion of the output

`PUT /task/status/<task-id>`: update the task status

`GET /task/user`: shows all the tasks executed by the current authenticated user

## Roadmap
