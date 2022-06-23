# Inputs, Outputs, Parameters

## Passing parameters between transitions
* Reference the `$.Payload.body.<var>` to get the upstream value from lambda

### Choice Statements
* Can add logic in definition without having to introduce new code

### Result Path and Output Path
* Can save input into `ResultPath` and then define `OutpuPath` to set an ouput key
