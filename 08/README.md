# Chapter 8: Networking
Try if you can get the exercises done. You can find more information in the `sources` directory.


Before beginning: Make sure to switch back to the namespace `default`

## Exercise 1:

The goal of this exercise is to create a deployment and a service to demonstrate it's service / loadbalancing capabilities.

1. Create a deployment called `hello-from-pod` with image `ghcr.io/michaeltrip/hello-from-pod:latest` with `3` replicas on port `8080`
2. Create a service called `hello-from-pod` with type `LoadBalancer` that listens on port `80`. The pods in the deployment `hello-from-pod` listen on port `8080`.
3. start `minikube tunnel` in a new terminal window. Don´t close it!
4. try to visit the external ip with your own browser on your own laptop/pc.
5. Refresh a few times. What do you see?
6. now start a curl client within Kubernetes with `kubectl run -it --rm client --image=curlimages/curl --image-pull-policy=Always -- /bin/sh`. now enter the interactive shell and try to `curl http://hello-from-pod` a few times.
7. You have visited both the web page through a external ip from your browser on your laptop / desktop and from within Kubernetes. You will see some different things: When visiting the webpage from within the Kubernetes cluster you will see the hostname change a lot. That is because of the round robin loadbalancing that is done by iptables. If you visit the webpage from a external IP (LoadBalancer) the session will stick through `SessionAffinity`, so in most cases you will only see one hostname / pod name.

In normal situations it is advised to use something like a ingress controller. Because of the limitations from within Minikube.

