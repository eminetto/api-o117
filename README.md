# API Observability

## Using the services

### Auth

```
curl -X "POST" "http://localhost:8081/v1/auth" \
     -H 'Accept: application/json' \
     -H 'Content-Type: application/json' \
     -d $'{
  "email": "eminetto@email.com",
  "password": "12345"
}'

```

The result should be a token, like:

```
{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6ImVtaW5ldHRvQGVtYWlsLmNvbSIsImV4cCI6MTY4MDcwODA1NSwiaWF0IjoxNjgwNzA0NDI1LCJuYmYiOjE2ODA3MDQ0MjV9.LB064HaSfumhNh_PirSEJqDB1sYgHt2U6HDTjyH1nog"
}
```

### Feedback

You need to use the token generated by the ```Auth``` service:

```
curl -X "POST" "http://localhost:8082/v1/feedback" \
     -H 'Accept: application/json' \
     -H 'Content-Type: application/json' \
	 -H 'Authorization:eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6ImVtaW5ldHRvQGVtYWlsLmNvbSIsImV4cCI6MTY4MDcwODA1NSwiaWF0IjoxNjgwNzA0NDI1LCJuYmYiOjE2ODA3MDQ0MjV9.LB064HaSfumhNh_PirSEJqDB1sYgHt2U6HDTjyH1nog' \
     -d $'{
  "title": "Feedback test",
  "body": "Feedback body"
}'
```

### Vote

You need to use the token generated by the ```Auth``` service:

```
curl -X "POST" "http://localhost:8083/v1/vote" \
     -H 'Accept: application/json' \
     -H 'Content-Type: application/json' \
	 -H 'Authorization:eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6ImVtaW5ldHRvQGVtYWlsLmNvbSIsImV4cCI6MTY4MDcwODA1NSwiaWF0IjoxNjgwNzA0NDI1LCJuYmYiOjE2ODA3MDQ0MjV9.LB064HaSfumhNh_PirSEJqDB1sYgHt2U6HDTjyH1nog' \
     -d $'{
  "talk_name": "Go e Microserviços",
  "score": "10"
}'
```

