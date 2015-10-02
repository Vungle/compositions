# compositions

## Prereqs

* docker
* docker-compose
* good internet

## Start

`docker-compose -f metronome.yml up -d`


## Access Grafana

`docker_machine_ip:300` login as admin/admin

## Add the influx db as your data source

Host: `http://influxdb:8096`
DB Name: `stats`
DB User: `root`
DB Pass: `root`


## Test

Send a test metric `echo "deploys.adserver.myservice:1|c" | nc -w 1 -u docker_machine_ip 8125`
