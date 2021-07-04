![Build Image and Push to Dockerhub](https://github.com/mikemartin1090/aws-cli/workflows/Build%20Image%20and%20Push%20to%20Dockerhub/badge.svg)

# Overview
A weekly build of the latest AWS CLI with the session manager plugin and stored on DockerHub.

An example of how to run it:
```bash
docker run --rm -it \
-v ~/.aws:/root/.aws \
-v $(pwd):/aws \
--env AWS_SESSION_TOKEN \
--env AWS_ACCESS_KEY_ID \
--env AWS_SECRET_ACCESS_KEY \
--env AWS_DEFAULT_REGION \
--env AWS_PAGER="" \
mikemartin1090/aws-cli \
s3 ls # AWS command of your choice
```

One thing I personally do is set it as an environment alias:
```
alias aws='docker run --rm -it -v ~/.aws:/root/.aws -v $(pwd):/aws --env AWS_SESSION_TOKEN --env AWS_ACCESS_KEY_ID --env AWS_SECRET_ACCESS_KEY --env AWS_DEFAULT_REGION --env AWS_PAGER="" mikemartin1090/aws-cli'
```

 This allows me to run commands as I normally would, but using the Docker image instead. I no longer need to locally install the AWS CLI:
 ```
aws s3 ls
 ```