# Building Your Kubernetes Cluster

## This will go over the order in which you would deploy all these files and some pre-requisite commands for them

### Helm

-   Use the following commands if you have never deployed or build an ingress for a project in gcp

```bash
helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx
helm repo update
```

-   Use this command every time you want to deploy via an ingress. This will create the external load-balancer that connects to the ingress.

```bash
helm install ingress ingress-nginx/ingress-nginx
```

### Linking the IAM permissions of a Service Account to a Kubernetes Service Account

-   Below shows how we link the

```bash
#overall structure
gcloud iam service-accounts add-iam-policy-binding --role roles/iam.workloadIdentityUser --member "serviceAccount:workloadidentitynamespace[default/ksa]" emailaddressofservicacount

#example from this project
gcloud iam service-accounts add-iam-policy-binding --role roles/iam.workloadIdentityUser  --member "serviceAccount:projectnamehere.svc.id.goog[default/logging-writer]" logging-writer@projectnamehere.iam.gserviceaccount.com
```

### Deploying the kubernetes files

-   Order of Deployment goes as follows

    1. Object creation required by other files
        ```bash
            kubectl apply -f hello-logger-sa.yaml
            kubectl apply -f hello-secret.yaml
            kubectl apply -f hello-pvc.yaml
        ```
    2. All deployments/pod files that reference your containers.

        ```bash
            #if you use the pod
            kubectl apply -f hello-app-pod.yaml

            # if you use all deployments
            kubectl apply -f hello-app-deployment.yaml
            kubectl apply -f hola-app-deployment.yaml
        ```

    3. All service files to access your pods.
        ```bash
            # Reminder to check if using type ClusterIP if you are utilizing an ingress as this is required
            kubectl apply -f hello-service.yaml
            kubectl apply -f hola-service.yaml
        ```
    4. (OPTIONAL) If deploying ingress
        ```bash
            # This will actually let your ingress know which services to contact via the ingress-controller
            kubectl apply -f ingress.yaml
        ```

### Common Practice

-   Store the yaml files within the root service directory.
-   If ingress.yaml is being deployed you can include the entire ingress.yaml in each service deployed to kubernetes as a reference
-   Write out the deployment commands incase someone wishes to deploy your project as well.
