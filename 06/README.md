# Chapter 5: Troubleshooting
Try if you can get the exercises done. You can find more information in the `sources` directory.

## Exercise 1:

This is all about troubleshooting pods:

1. Apply the manifests `wrong1.yaml`, `wrong2.yaml` and `wrong3.yaml`
2. try to solve the errors! ;-)
3. Delete the pods if they work.

## Exercise 2:

This is all about troubleshooting inside a pod.

1. Apply the apache webserver manifest called `apa.yaml`
2. Execute a interactive shell in the container. Hint: `kubectl exec --help`.
3. Try to view all processes running in the container
4. Try to view all open listen ports in this container with the `ss -tl` command. Hint: It could be that this command is not available. Try installing it.
5. Delete the pods

