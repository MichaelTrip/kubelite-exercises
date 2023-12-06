# Chapter 7: Storage
Try if you can get the exercises done. You can find more information in the `sources` directory.


Before beginning: Make sure to switch back to the namespace `default`

## Exercise 1:

The goal of this exercise is to create a Persistent Volume claim (pvc) and mount it into a pod.

1. create a Persistent Volume claim called `shared-data` with with AccesMode `ReadWriteMany`. You can use the `StorageClass` called `standard`. You can use the base yaml called `pvc.yaml` in the `sources` directory.
2. Create a pod called `nginx-webserver` with image `nginx:latest`. Mount the directory `/usr/share/nginx/html` to the created pvc.
3. Create a pod called `apache-webserver` with image `httpd:latest`. Mount the directory `/usr/local/apache2/htdocs` to the created pvc.
4. Execute a interactive shell in one of the pods and do a echo `hello-world` to a file `index.html` to the mounted directory.
5. After that, you can test the results. Create a temporary pod called `client` with image `=curlimages/curl:latest` and verify it with `curl http://pod-ip`. hint: Note the pods ip and try it. What do you see? Hint: `kubectl run -it --rm client --image=curlimages/curl:latest -- /bin/sh`
6. Delete the pod and pvc

