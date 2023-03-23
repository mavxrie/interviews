# Kubernetes Interview

Base files for kubernetes interview.

## Set-up

Most of the interview will be done using [kind](https://kind.sigs.k8s.io/). Make sure to spawn a simple cluster with this multi-node configuration file (store it as `kind-cluster.yaml`):

```yaml
kind: Cluster
apiVersion: kind.x-k8s.io/v1alpha4
nodes:
- role: control-plane
- role: worker
- role: worker
```

Create the cluster with the command:

```sh
$ kind create cluster --name testaroo --config kind-cluster.yaml
```

Verify the cluster is up & running:

```sh
$ kubectl get node
NAME                     STATUS   ROLES           AGE     VERSION
testaroo-control-plane   Ready    control-plane   3h35m   v1.25.3
testaroo-worker          Ready    <none>          3h35m   v1.25.3
testaroo-worker2         Ready    <none>          3h35m   v1.25.3
```

## Clean-up

Delete the cluster with simply:

```sh
$ kind delete cluster --name testaroo
```