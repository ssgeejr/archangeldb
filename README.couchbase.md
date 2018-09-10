# Couchbase Database Setup for microservice testing



docker exec -it db sh
echo "export PATH=/opt/couchbase/bin:$PATH" >> /etc/profile
. /etc/profile
cbimport csv -c localhost -u Administrator -p password -b archangel -d file://mock_data.csv --generate-key key::%id%



SELECT archangel.* FROM archangel;


code": 400, "msg": "No index available on keyspace archangel that matches your query. Use CREATE INDEX or CREATE PRIMARY
............................--> table<column,column(s)>
CREATE INDEX idx_tp_app_mt ON archangel(id) USING VIEW;

https://docs.couchbase.com/server/5.5/install/getting-started-docker.html
docker run -t --name db -v couchbase-vol:/opt/couchbase/var -p 8091-8094:8091-8094 -p 11210:11210 couchbase/server-sandbox:5.5.0


select * from archangel where id = "101";



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
cbimport csv -c localhost -u Administrator -p password -b archangel -d file://mock_data.csv --generate-key key::%id%

/opt/couchbase/var

--name db -v ~/couchbase:/opt/couchbase/var

--generate-key invoiceitem::#UUID#

mongoexport --host localhost --db sku --collection gsma --type=json > test.json
mongoexport --host localhost --db sku --collection gsma --type=json > test.json

docker cp archangeldb:/test.json /opt/dev/test.json

/opt/couchbase/bin/tools/cbdocloader -u Administrator -p password -n 10.3.2.54:8091 -b bucket -s 1000 output

##--------------------------------------------------------------------------
https://docs.couchbase.com/server/5.5/install/getting-started-docker.html
docker run -d --name db -p 8091-8096:8091-8096 -p 11210-11211:11210-11211 couchbase


cbdocloader  -n [localhost]:8091 -u [Administrator] -p [password] -b [bucket-name] [source-file]



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





