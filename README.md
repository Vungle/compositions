# compositions

## Prereqs

* docker
* docker-compose
* good internet

## Start

`docker-compose -f metronome.yml up -d`


## Access Grafana

Open your browser to `docker_machine_ip:3000` 

login as admin/admin

## Add the influx db as your data source

Host: `http://influxdb:8096`
DB Name: `stats`
DB User: `root`
DB Pass: `root`


## Test

Send a test metric `echo "deploys.adserver.myservice:1|c" | nc -w 1 -u docker_machine_ip 8125`

## Validate

To validate the stats are being picked up do: `docker-compose logs statsd` and you should get a stream of stats coming in.
