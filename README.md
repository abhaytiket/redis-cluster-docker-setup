# redis-cluster-docker-setup
Setup redis cluster similar to staging and production environments using docker-compose on your local machine. Staging setup will have 3 master nodes with no slaves. Production setup will have 3 master and 3 slave nodes i.e. 1 slave for each master. Make sure you have docker and docker-compose installed on your machine. 

To setup a cluster similar to production environment use command
```
$ docker-compose -f docker-compose.production.yml up
```
on your terminal.

To setup a cluster similar to staging environment use command
```
$ docker-compose -f docker-compose.staging.yml up
```
on your terminal.

To destroy the cluster for production environment ise command
```
$ docker-compose -f docker-compose.production.yml down
```
on your terminal.

To destroy the cluster for staging environment ise command
```
$ docker-compose -f docker-compose.staging.yml down
```
on your terminal.
