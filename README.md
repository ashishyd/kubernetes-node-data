`empty_dir` volume creates an empty directory on mounted volume path inside pod

It fails if we user Replicas > 1 as then other replica will not have same data in empty directory

`hostpath` solve the above problem with the path will be on worker node. It can only work on single node cluster like minikube

`csi (container storage interface)` is provided by AWS EFS through which we can use EFS storage easily. In future other cloud storage can also implement CSI interface

`PersistentVolume` are inside the cluster not in nodes or containers. They work on `PV claim`.

To create persistent volume we need to a new configuration `host-pv.yaml`

To use this persistent volume we need a new configuration for claim `host-pvc.yaml`

`Storage Class` are checked using `kubectl get sc`

To get all persistent volumes `kubectl get pv`

To get all persistent volume claims `kubectl get pvc`

You can create config map configuration if you want to specify environment variables, which can be checked using `kubectl get configmap`