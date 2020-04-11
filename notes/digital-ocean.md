# Digital Ocean

Referral Link: [https://m.do.co/c/001ed2c46f75](https://m.do.co/c/001ed2c46f75)

## Kubernetes

### nfs-provisioner

Reason:

* I don't want to have lots of small pieces of Digital Ocean Block Storage volumes
* Enables `ReadWriteMany` for sharing files across pods

Links:

* [nfs-provisioner](https://github.com/kubernetes-incubator/external-storage/tree/master/nfs)
* [How to setup nfs-provisioner on Digital Ocean using Helm](https://www.digitalocean.com/community/tutorials/how-to-set-up-readwritemany-rwx-persistent-volumes-with-nfs-on-digitalocean-kubernetes)

#### Resizing nfs-provisioner

Links:

* [How to increase disk size in a stateful set](https://serverfault.com/questions/955293/how-to-increase-disk-size-in-a-stateful-set)
* [Resizing persistent volumes using kubernetes](https://kubernetes.io/blog/2018/07/12/resizing-persistent-volumes-using-kubernetes/)

{% hint style="danger" %}
There will be downtime
{% endhint %}

Edit the Persistent Volume Claim to 

```bash
kubectl edit pvc data-nfs-server-nfs-server-provisioner-0
```

Assuming we are changing from `5Gi` to `10Gi`

Change the keys for:

* `spec.resources.request.storage`
* `status.capacity.storage`

```diff
  spec:
    resources:
      requests:
-      storage: 5Gi
+      storage: 10Gi
  status:
    capacity:
-      storage: 5Gi
+      storage: 10Gi
```

Delete the StatefulSet:

```bash
kubectl delete sts --cascade=false nfs-server-nfs-server-provisioner
```

Change your helm custom values, I store mine in a `custom.yaml` file.

```diff
  persistence:
-   size: 5Gi
+   size: 10Gi
```

Apply changes in helm

```bash
helm upgrade nfs-server nfs-server-provisioner/ -f nfs-server-provisioner/custom.yaml
```

