# Chapter 5: Objects
Try if you can get the exercises done. You can find more information in the `sources` directory.


Before beginning: Make sure to switch back to the namespace `default`

## Exercise 1:

This is all about deployments and rollouts:

1. View the contents of the manifest file called `bing-deploy.yaml` and try to apply this deployment with the `--record` option.
2. View The status of the rollout: Hint: `kubectl rollout --help`
3. View the log of one of the pods. Pay attention to what you see!
4. Modify the value `Europe/Amsterdam` (environment variable TZ) to `Europe/Lisbon` in the manifest file and apply the modification with `kubectl` to the running deployment with the option `--record` added.
5. View the status of all objects again. What happened? hint: check `kubectl get pods -w`
6. Check the logs again: What do you see now?
7. Edit the deployment object with the command `kubectl edit ... --record` (add the option `--record` for a relevant change cause in the history), modifying the value `Europe/Lisbon` to `Europe/Athens` now. View the status of all objects after finishing the edit session.
8. Finally, modify the value of the environment variable TZ to Europe/Rome with the command `kubectl set env ....` (unfortunately the option `--record` is not accepted here). View the status of all objects.

Notice that the active deployment deviates from the manifest file now!

## Exercise 2:

This is all about the rollout history and how to undo rollout of new deployments:

1. View the rollout history. Hint: `kubectl rollout --help`
2. View the specific settings of revision 2 and confirm that the environment: variable TZ has the value `Europe/Lisbon` for that specific revision. Hint: `kubectl rollout history .... --revision <number>`
3. Rollback to revision 2 and view the rollout history again. Hint: `kubectl rollout undo --help`
4. View the status of all objects.
5. Delete the deployment.

## Exercise 3:

This is all about parallelism of jobs:

1. View the contents of the manifest file `random-job.yaml`.
2. apply the manifest file.
3. Watch the progress of this job with the command `kubectl get job -w`. How long does it take to generate 20 random numbers without parallelism?
4. View the status of this job and the pods after the job is complete. Also view the summary of the pod statusses and the duration of the job with the command `kubectl describe ...`.
5. Delete the job
6. Modify the `parallelism` to 5 in the manifest file of the job and create (apply) the job again.
7. Watch the progress of the job with the command `kubectl get job -w`. How long does it take to generate 20 random numbers now with parallelism?
8. Delete the job

## Exercise 4:

This is all about job completions and limits of the job:

1. View the contents of the `oknok-job.yaml` manifest file. The command that is started in this container randomly gives exit code 0 (correct completion) or 1 (incorrect completion).
2. Create (apply) the job defined in this manifest file.
3. Watch the progress of this job by running the command `kubectl get job,pod` periodically. At a certain moment the number of pod completions will be 3.
4. Delete the job
5. Modify the backoffLimit to 2 and the completions to 30 in the manifest file.
6. Create (apply) the job defined in this manifest file again and watch the progress of this job periodically. When you have the impression that pods are not activated any more, have a look at the job with the command
`kubectl describe ...`
What is the reason of the stand-still?
7. Delete the job


