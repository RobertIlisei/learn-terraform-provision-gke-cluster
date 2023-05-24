# Steps to deploy a MySQL database on KBE

// Assuming we have a KBE cluster already deployed and a name space create for our database

1) Create secret file containing the password of root user for the database
2) Create the PVC config file 
3) Create the config-map file
4) Create the deployment file
5) Create the service file

# Testing the database

    kubectl exec --stdin --tty pod/mysql-deploy-6b5b559f57-gjrrm -- /bin/bash
    mysql -p #enter the password defined in the secret configuration

