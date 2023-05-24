# Get argocd secret password:

    kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d; echo

# Login to argocd  on CLI

    argocd login localhost:8080
    https://localhost:8080/applications/

# creat argocd-manager 

    argocd cluster add gke_kubernetes-387518_europe-west3_kubernetes-387518-gke
    // WARNING: This will create a service account `argocd-manager` on the cluster referenced by context `gke_kubernetes-387518_europe-west3_kubernetes-387518-gke` with full cluster level privileges

# Sync the helm-guestbook

    argocd app sync helm-guestbook

#  Portforward for helm-guestbook 

    kubectl port-forward svc/helm-guestbook 9090:80
    https://localhost:9090