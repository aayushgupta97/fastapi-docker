# fastapi-docker

#### * To access db via psql
```docker-compose exec web-db psql -U postgres```

```\c web_dev```


#### * To run the test cases
```docker-compose exec web python -m pytest```


#### * To generate the db schema
```docker-compose exec web python app/db.py```




## Requests

1) Summary POST: 
```
curl -X 'POST' 'http://localhost:8004/summaries/' -H 'accept: application/json' -H 'Content-Type: application/json' -d '{"url": "https://www.google.com"}'
```



## Pytest commands

#### normal run
$ docker-compose exec web python -m pytest

#### disable warnings
$ docker-compose exec web python -m pytest -p no:warnings

#### run only the last failed tests
$ docker-compose exec web python -m pytest --lf

#### run only the tests with names that match the string expression
$ docker-compose exec web python -m pytest -k "summary and not test_read_summary"

#### stop the test session after the first failure
$ docker-compose exec web python -m pytest -x

#### enter PDB after first failure then end the test session
$ docker-compose exec web python -m pytest -x --pdb

#### stop the test run after two failures
$ docker-compose exec web python -m pytest --maxfail=2

#### show local variables in tracebacks
$ docker-compose exec web python -m pytest -l

#### list the 2 slowest tests
$ docker-compose exec web python -m pytest --durations=2