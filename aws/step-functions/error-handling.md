# Error Handling

## State Errors
* States.ALL -> If one fails, who thing fails
* States.Runtime -> Not retryable
* States.Timeout -> Task exceeds time
* States.TaskFailed and States.Permissions

## Lambda Specific
* Lambda.Unkown
* Lambda.Exception
* Lambda.ServiceException

## Lambda Timeouts
* Want to know why it takes too long
* `TimeoutSeconds`

## Error Handling

### Retries
```
"Retry":[{ "ErrorEuals": ["States.Timeout"],
```
* low number max attemps

### Catching
```
"ErrorEquals": ["States.ALL"],
"Next": "End State"
```


