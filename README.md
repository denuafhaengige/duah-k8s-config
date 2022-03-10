# duah-k8s-config

Repository containing fluxv2 compatible cluster provisioning manifests.

## Run book

Running the following example bootstraps a cluster, making it ready to receive traffic within 10min.

```console
x@y:~$ export GITHUB_TOKEN=<YOUR_GITHUB_TOKEN>
x@y:~$ export GITHUB_USER=<YOUR_GITHUB_USER>
x@y:~$ flux bootstrap github \                    
         --owner=denuafhaengige \
         --components-extra=image-reflector-controller,image-automation-controller \
         --repository=duah-k8s-config \
         --read-write-key \
         --path=./clusters/<YOUR_VARIANT>
```

Make sure to replace the placeholders in the example above. See the following table to reference:
| Placeholder       | Type       | Explanation                                                   |
| ----------------- |:----------:| -------------------------------------------------------------:|
| YOUR_GITHUB_TOKEN | string     | Personal access token for your Github account                 |
| YOUR_GITHUB_USER  | string     | Username for your Github account                              |
| YOUR_VARIANT      | blue/green | Either blue or green. Changes which public IPs are associated |
