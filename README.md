

# MySQl server with kubernetes

## How to create a MYSQL service

(1) Create the pod:
```
$ kubectl create -f mysql.yaml
```

(2) Viewing the created pod
```
$ kubectl get pods
POD       IP            CONTAINER(S)   IMAGE(S)   HOST                            LABELS       STATUS    CREATED
mysql     172.17.38.2   mysql          mysql      192.168.50.132/192.168.50.132   name=mysql   Running   3 hours
```

(3) Start the service:
```
kubectl create -f mysql-service.yaml
```

(4) Find the service
```
$ kubectl get services


mysql           name=mysql                                name=mysql   10.254.13.156    3306/TCP
                                                                       192.168.50.132
```

(5)Let’s connect to our database server from outside

mysql -uroot -p -h192.168.50.132



How to delete the pod and service

```
kubectl delete rc mysql
kubectl delete service mysql
```

