# Chapter 4: Management
Try if you can get the exercises done. You can find more information in the `sources` directory.


Before beginning: Make sure to switch back to the namespace `default`

## Exercise 1:

1. Run the command `kubectl apply -f apa.yaml`
2. Try to apply the label `application=webserver` to the pod called `apatest` with the `kubectl` command.
3. Check if the label is applied correctly with the `kubectl` command.
4. Remove the label `application=webserver` with the `kubectl` command.
5. Delete the pod `apatest`


## Exercise 2:

1. Try to modify the manifest file called `apa.yaml` and try to add the label `application=webserver` again.
2. Also add a annotation `owner: John` to the manifest file
3. Apply the manifest file with `kubectl apply -f apa.yaml`
4. Can you see the label applied to the pod?
5. Can you see the annotation applied to the pod? Hint: `kubectl describe`
6. Try to overwrite the annotation with the kubectl command from `owner: John` to `owner: Kate`
7. Delete the pod `apatest`
