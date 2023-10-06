```
docker compose up
```

check sqs queues


- localstack/localstack:2.2

```
AWS_ACCESS_KEY_ID=test AWS_SECRET_ACCESS_KEY=test aws sqs list-queues --endpoint http://localhost:54566
{
    "QueueUrls": [
        "http://localhost:54566/000000000000/my-sample-queue"
    ]
}
# ok. it works.
```


- localstack/localstack:2.3.0

```
AWS_ACCESS_KEY_ID=test AWS_SECRET_ACCESS_KEY=test aws sqs list-queues --endpoint http://localhost:54566
#=> No response. However, the console on the localstack side shows the log of accepted requests.
#   localstack-check-localstack-1  | 2023-10-06T06:18:45.923  INFO --- [   asgi_gw_0] localstack.request.aws     : AWS sqs.ListQueues => 200
```