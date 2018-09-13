# AWS CLI in Docker

Containerized AWS CLI and other tools based on latest python to avoid requiring the aws cli to be installed on CI machines.

## Build

```
docker build -t stevehouel/docker-aws-tools .
```

Automated build on Docker Hub

[![DockerHub Badge](http://dockeri.co/image/stevehouel/docker-aws-tools)](https://hub.docker.com/r/stevehouel/docker-aws-tools/)

## Usage

Configure:

```
export AWS_ACCESS_KEY_ID="<id>"
export AWS_SECRET_ACCESS_KEY="<key>"
export AWS_DEFAULT_REGION="<region>"
```


## Install

Add an alias to your shell:


alias aws='docker run --rm -e "AWS_ACCESS_KEY_ID=${AWS_ACCESS_KEY_ID}" -e "AWS_SECRET_ACCESS_KEY=${AWS_SECRET_ACCESS_KEY}" -e "AWS_DEFAULT_REGION=${AWS_DEFAULT_REGION}" -v "$(pwd):/app" stevehouel/docker-aws-tools'


## Maintenance

- The Docker image build & publish is automated by DockerHub for master commits and tags.

## References

AWS CLI Docs: https://aws.amazon.com/documentation/cli/
AWS SAM CLI Docs: https://docs.aws.amazon.com/lambda/latest/dg/sam-cli-requirements.html
