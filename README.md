# ECS Deployment Script

This script waits for an Amazon ECS service to [become stable](https://docs.aws.amazon.com/cli/latest/reference/ecs/wait/services-stable.html) after a deployment, such as in a CD pipeline deployment step. The functionality of this script is similar to `aws ecs wait services-stable`, except that it provides a configurable polling interval, configurable timeout, and verbose output.

Like `aws ecs wait services-stable`, this script considers a service stable when there is one service deployment and that deployment's running count of tasks equals its desired count. The script exits with an error code when a timeout occurs.

> Note: This script uses the `aws` and `jq` commands, expecting them in the path.

