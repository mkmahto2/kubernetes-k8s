### kubectl

```
curl -LO https://storage.googleapis.com/kubernetes-release/release/`curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt`/bin/linux/amd64/kubectl
mv kubectl /usr/bin/
chmod +x /usr/bin/kubectl
```
### using it 
```
#To check version
$~kubectl version
#To Check Number of Nodes
$~kubectl get node

```
### Check that kubectl is correctly installed and configured by running the kubectl cluster-info command:
```
kubectl cluster-info

```
### Crearing the pod file
```
$~kubectl create -f podfile.yml
#above cmd will not create if already pod exist
#We can use apply cmd it will try to create pod again same and also will update if it there
$~kubectl apply -f podfile.yml
##check status
$~kubectl get pods
#-w for watching live
$~kubectl get pods -w
###checking IP of POD , Node where it scheduled
~>>kubectl get pods -o wide
## delete POD
$~kubectl delete pod podname
##rather than get pod we can use describe for detailed infomation
$~kubectl describe pods podname
```

#### Getting help for kubectl 

```
$~kubectl explain pods | less
#for API Version
$~kubectl explain pods.apiVersion | less
## for metadata
$~kubectl explain pods.metadata | less
## also for particular field like container in Specs
$~kubectl explain pods.spec.containers
$~kubectl explain pods.spec.containers.ports ##now also ports inside containers
```