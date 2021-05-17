# GSP305 : Scale Out and Update a Containerized Application on a Kubernetes Cluster

```bash
gsutil cp gs://sureskills-ql/challenge-labs/ch05-k8s-scale-and-update/echo-web-v2.tar.gz .
```

```bash
tar xvzf echo-web-v2.tar.gz
```

```bash
gcloud builds submit --tag gcr.io/$DEVSHELL_PROJECT_ID/echo-app:v2 .
```

```bash
gcloud container clusters get-credentials echo-cluster --zone us-central1-a
```

```
kubectl create deployment echo-web --image=gcr.io/qwiklabs-resources/echo-app:v1
```

```
kubectl expose deployment echo-web --type=LoadBalancer --port 80 --target-port 8000
```

```
kubectl edit deploy echo-web
```

### Change image version 'v1' to 'v2' by pressing "i"

### Save by pressing - Esc -amd then type ":wq"

```
kubectl scale deploy echo-web --replicas=2
```
