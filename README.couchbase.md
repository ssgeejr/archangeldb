# Couchbase Database Setup for microservice testing

docker exec -it db sh
echo "export PATH=/opt/couchbase/bin:$PATH" >> /etc/profile
. /etc/profile
cbimport csv -c localhost -u Administrator -p password -b archangel -d file://mock_data.csv --generate-key key::%car_model%
docker

docker exec -it db sh
echo "export PATH=/opt/couchbase/bin:$PATH" >> /etc/profile
. /etc/profile
cbimport csv -c localhost -u Administrator -p password -b archangel -d file://mock_data.csv --generate-key key::%id%

/opt/couchbase/bin/cbq -c localhost --script="CREATE INDEX indx_acm ON archangel(car_model) USING VIEW;"
/opt/couchbase/bin/cbq --script="CREATE INDEX indx_acm ON archangel(car_model) USING VIEW;"


./cbq --script="CREATE INDEX idx_tp_app_mt ON archangel(car_model) USING VIEW;"

SELECT archangel.* FROM archangel;


code": 400, "msg": "No index available on keyspace archangel that matches your query. Use CREATE INDEX or CREATE PRIMARY
............................--> table<column,column(s)>
CREATE INDEX idx_tp_app_mt ON archangel(id) USING VIEW;

https://docs.couchbase.com/server/5.5/install/getting-started-docker.html
docker run -t --name db -v couchbase-vol:/opt/couchbase/var -p 8091-8094:8091-8094 -p 11210:11210 couchbase/server-sandbox:5.5.0


select * from archangel where id = "101";

git remote rm origin
git remote add origin git@github.com:ssgeejr/archangeldb.git
cd ../archangelms
git remote rm origin
git remote add origin git@github.com:ssgeejr/archangelms.git
cd ../archangelui
git remote rm origin
git remote add origin git@github.com:ssgeejr/archangelui.git





cd 
cd /opt/dev/archangelprj/archangeldb
cd /opt/dev/archangelprjc
cd /opt/dev/archangelprj/archangelui


#!/bin/bash
## declare an array variable
declare -a array=("/opt/dev/archangelprj" 
"/opt/dev/archangelprj/archangeldb" 
"/opt/dev/archangelprj/archangelms" 
"/opt/dev/archangelprj/archangelui" 
)

for i in "${arr[@]}"
do
   echo "$i"
   # or do whatever with individual element of the array
done


/opt/couchbase/bin
/opt/couchbase/bin


localhost:8091
Username: Administrator
Password: password

SELECT country FROM `travel-sample` WHERE name = "Excel Airways";

export PATH=/opt/couchbase/bin:$PATH" > /etc/profile
. /etc/profile

RUN echo "export PATH=/opt/couchbase/bin:$PATH" > /etc/profile && \
 . /etc/profile


Try the Interactive Query Shell
bash -c "clear && docker exec -it db sh"

cd /opt/couchbase/bin
./cbq -u Administrator -p password -engine=http://127.0.0.1:8091/

cbq> SELECT callsign FROM `travel-sample` LIMIT 5;

cbq> SELECT * FROM `travel-sample` WHERE type="airport" LIMIT 1;

https://docs.couchbase.com/server/5.5/tools/cbimport.html
volumes:
    mysql-data
http://<ip>:8091
key::%id%

docker exec -it db sh
echo "export PATH=/opt/couchbase/bin:$PATH" >> /etc/profile
. /etc/profile
cbimport csv -c localhost -u Administrator -p password -b archangel -d file://mock_data.csv --generate-key key::%car_model%
docker

/opt/couchbase/var

--name db -v ~/couchbase:/opt/couchbase/var

--generate-key invoiceitem::#UUID#

mongoexport --host localhost --db sku --collection gsma --type=json > test.json
mongoexport --host localhost --db sku --collection gsma --type=json > test.json

docker cp archangeldb:/test.json /opt/dev/test.json


XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX SCRIPT XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
docker cp docker/mock_data.csv db:/mock_data.csv
docker cp seeddb db:/seeddb

docker exec -ti db /seeddb


/opt/couchbase/bin/couchbase-cli bucket-create -c localhost:8091 -u Administrator -p password --bucket=archangel --bucket-type=couchbase --bucket-ramsize=200

/opt/couchbase/bin/cbimport csv -c localhost -u Administrator -p password -b archangel -d file://mock_data.csv --generate-key key::%car_model%

--generate-key key::%car_model%

CREATE INDEX abv_idx ON `beer-sample`(abv);

##--------------------------------------------------------------------------
https://docs.couchbase.com/server/5.5/install/getting-started-docker.html
docker run -d --name db -p 8091-8096:8091-8096 -p 11210-11211:11210-11211 couchbase


412



cbdocloader  -n [localhost]:8091 -u [Administrator] -p [password] -b [bucket-name] [source-file]

Administrator / password

version: '3.4'
services:
    couchbase:
        image: 'couchbase/server-sandbox:5.5.0'
        container_name: db
        labels:
            maintainer: 'Steve S Gee Jr <ioexcept@gmail.com>'
        ports:
            - '8091-8094:8091-8094'
            - '11210:11210'
        volumes:
            - 'couchbase-vol:/opt/couchbase/var'
        tty: true
        stdin_open: true
        restart: always
volumes:
    couchbase-vol:





