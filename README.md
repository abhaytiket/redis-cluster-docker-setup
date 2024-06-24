# redis-cluster-docker-setup
Setup redis cluster similar to staging and production environments using docker-compose on your local machine. Staging setup will have 3 master nodes with no slaves. Production setup will have 3 master and 3 slave nodes i.e. 1 slave for each master. Make sure you have docker and docker-compose installed on your machine. To know the host ip for your machine please execute following command first on your Mac terminal
```
$ echo "$(route get uninterrupted.tech | grep interface | sed -e 's/.*: //' | xargs ipconfig getifaddr)"
```

Then replace the ip in `docker-compose.xxx.yml` file with the ip in output of previous command.

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

After your cluster has started running you can use a client like [Medis](https://getmedis.com/) on your Mac to connect with the cluster using host ip as the one in the output of
```
$ echo "$(route get uninterrupted.tech | grep interface | sed -e 's/.*: //' | xargs ipconfig getifaddr)"
```
As far as port is concerned you can select any port of a node. Just make sure that your client is cluster aware.


**NOTE: While starting the cluster of in case sometimes you get an error message as `waiting for all the nodes to be ready` on your terminal then terminate execution of your docker-compose, remove all containers for the services and then retry.**
