

### Install, Uninstall, List
- To install
```
# MySQL
helm install --dry-run mysql-db -n sqldb . -f dev/values.yaml
helm install mysql-db -n sqldb . -f dev/values.yaml -f dev/secrets.yaml --create-namespace
helm ls -n sqldb

# phpMyAdmin
helm install phpadmin-app -n phpmyadmin . -f dev/values.yaml -f dev/secrets.yaml --create-namespace
helm ls -n phpmyadmin

# NGINX
helm install nginx-proxy -n nginx . -f dev/values.yaml --create-namespace
helm ls -n nginx
```

- To upgrade 
```
# MySQL
helm upgrade mysql-db -n sqldb . -f dev/values.yaml -f dev/secrets.yaml

# phpMyAdmin
helm upgrade phpadmin-app -n phpmyadmin . -f dev/values.yaml -f dev/secrets.yaml

# NGINX
helm upgrade nginx-proxy -n nginx . -f dev/values.yaml
```

- To Uninstall 
```
helm uninstall mysql-db -n sqldb
helm uninstall phpadmin-app -n phpmyadmin
helm uninstall nginx-proxy -n nginx
```

- Basic codes
```
 kubectl get namespace
 kubectl get pods -n db
 kubectl get service -n nginx
```
 - ArgoCD
```
 
 kubectl port-forward service/argocd-server 8081:80 -n argocd
  
```