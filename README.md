# fastapi-docker

#### * To access db via psql
```docker-compose exec web-db psql -U postgres```

```\c web_dev```


#### * To run the test cases
```docker-compose exec web python -m pytest```


#### * To generate the db schema
```docker-compose exec web python app/db.py```