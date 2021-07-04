# Overview
A weekly build of the latest AWS CLI with the session manager plugin and stored on DockerHub.

A helpful way to run it:
```
docker run --rm -it \
-v ~/.aws:/root/.aws \
-v $(pwd):/aws \
--env AWS_SESSION_TOKEN \
--env AWS_ACCESS_KEY_ID \
--env AWS_SECRET_ACCESS_KEY \
--env AWS_DEFAULT_REGION \
--env AWS_PAGER="" \
mikemartin1090/aws-cli
```