# Chapter 1: introduction into Kubernetes

Installing Minikube: Read the readme: https://minikube.sigs.k8s.io/docs/start/

# Installing minikube

## Windows

### prerequisites

Install Hyper-V or Docker desktop:

- For Hyper-V see https://minikube.sigs.k8s.io/docs/drivers/hyperv/
- For Docker Desktop see https://minikube.sigs.k8s.io/docs/drivers/docker/

After that: Set your default driver to either Hyper-V or docker:

For Hyper-V:

`minikube config set driver hyperv`

For Docker:

`minikube config set driver docker`

### Installation

1. Install through Powershell

```
New-Item -Path 'c:\' -Name 'minikube' -ItemType Directory -Force
Invoke-WebRequest -OutFile 'c:\minikube\minikube.exe' -Uri 'https://github.com/kubernetes/minikube/releases/latest/download/minikube-windows-amd64.exe' -UseBasicParsing
```

2. Add `minikube.exe` to your `%PATH%`

```
$oldPath = [Environment]::GetEnvironmentVariable('Path', [EnvironmentVariableTarget]::Machine)
if ($oldPath.Split(';') -inotcontains 'C:\minikube'){
  [Environment]::SetEnvironmentVariable('Path', $('{0};C:\minikube' -f $oldPath), [EnvironmentVariableTarget]::Machine)
}
```

3. Start your cluster

```
minikube start
```

4. Install `kubectl.exe`

```
curl.exe -LO "https://dl.k8s.io/release/v1.28.4/bin/windows/amd64/kubectl.exe"
```
After that, move `kubectl.exe` somewhere into your `%PATH%`

5. Explore minikube

Initially, some services such as the storage-provisioner, may not yet be in a Running state. This is a normal condition during cluster bring-up, and will resolve itself momentarily. For additional insight into your cluster state, minikube bundles the Kubernetes Dashboard, allowing you to get easily acclimated to your new environment:

```
minikube dashboard
```

6. Try if you can find pods:

```
kubectl get pods -A
```
