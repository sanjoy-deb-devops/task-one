### Installing light weight kubernetes distribution (Kind):
1. download the binaries from official kind page 
`curl -Lo ./kind https://kind.sigs.k8s.io/dl/v0.14.0/kind-linux-amd64`
2. Change the file permission to execute
`chmod +x kind`
3. move the file to /usr/local/bin
`mv kind /usr/local/bin`
4. Create one yaml file  for one master and two worker node
`vi cluster-config.yaml`
~~~
# three node (two workers) cluster config
kind: Cluster
apiVersion: kind.x-k8s.io/v1alpha4
nodes:
- role: control-plane
- role: worker
- role: worker
~~~
5. Create the kubernetes cluster
`kind create cluster --config=cluster-config.yaml`
