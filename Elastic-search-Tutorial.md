# Elastic-Search basic tutorial

## Pre-requistes
1-follow this tutorial to install the ELK stack on a container 
   https://github.com/mahmoudrasmy/docker/blob/master/ELK-Container.md

## Basic Elastic search API calling
	1-To add data in the Elastic Search use or indexe data :
		curl -X POST http://Elastic-Search-IP:9200/logs/my_app -H 'Content-Type: application/json' -d '{"timestamp": "2015-01-18 12:34:56", "message": "User logged in", "user_id": 4, "admin": false}'
	
	2-To get the data by using the ID
		curl -X GET http://Elastic-Search-IP:9200/logs/my_app/ID
		
	3-To Delete a data 
		curl -X DELETE http://Elastic-Search-IP:9200/logs/my_app/ID