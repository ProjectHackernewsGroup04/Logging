# Guide to how use Kibana locally


### In case the master is not merged yet with new branch ("LoggingPatch") : 

1. Git pull everything 
2. Vagrant reload / ssh
3. cd /app/logging/
4. docker-compose up --build (to run logstash,kibana and elasticsearch)
5. cd /app/ 
6. docker-compose up -d database (Run database since backend need database to run)
7. cd /backend
8. docker-compose up -d backend (run backend)
9. goto http://localhost:5601
10. Browse kibana, but there is no any data yet so you cant do anything yet
11. inside vagrant : curl 0.0.0.0:5000/api/item/all (There is a log that will be revoked and send the message to logstash)
12. Now your kibana have data
13. You need to goto management menu and create a new index pattern by typing the wildcard "*"
![alt text](https://i.gyazo.com/86db78dee2cfd1b481730611ae23bbf8.png)

14. Click next step
15. Choose "I dont want use timefilter" as option 
16. click create index pattern
17. goto discovery in kibana
18. you should see a message with "API: getting all items"
![alt text](https://i.gyazo.com/ced607889b0d500e11b5de0fbcf41321.png)



### In case the master is merged with the new branch: 
1. cd /app/logging
2. docker-compose up
3. cd /app/
4. docker-compose up
9. goto http://localhost:5601
10. Browse kibana, but there is no any data yet so you cant do anything yet
11. inside vagrant : curl 0.0.0.0:5000/api/item/all (There is a log that will be revoked and send the message to logstash)
12. Now your kibana have data
13. You need to goto management menu and create a new index pattern by typing the wildcard "*"
![alt text](https://i.gyazo.com/86db78dee2cfd1b481730611ae23bbf8.png)

14. Click next step
15. Choose "I dont want use timefilter" as option 
16. click create index pattern
17. goto discovery in kibana
18. you should see a message with "API: getting all items"
![alt text](https://i.gyazo.com/ced607889b0d500e11b5de0fbcf41321.png)

