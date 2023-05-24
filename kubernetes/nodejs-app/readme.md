# Steps to deploy a MySQL database on KBE

// Assuming we have a K8S cluster and the MySQL database already deployed and a name space create for our app

1) Create secret file containing the password of root user for the database
2) Create the PVC config file
3) Create the config-map file
4) Create the deployment file
5) Create the service file




    gcloud container clusters get-credentials kubernetes-387518-gke --region europe-west3 --project kubernetes-387518 \
>  && echo "# When the next line says 'Forwarding from...', go to: https://ssh.cloud.google.com/devshell/proxy?port=8080" && kubectl port-forward --namespace mysql-api $(kubectl get pod --namespace mysql-api --selector="app=book-management,name=book-mgmt-api-pod" --output jsonpath='{.items[0].metadata.name}') 8080:5000