# drone-lambda

[![Build Status](http://beta.drone.io/api/badges/drone-plugins/drone-lambda/status.svg)](http://beta.drone.io/drone-plugins/drone-lambda)
[![](https://badge.imagelayers.io/plugins/drone-lambda:latest.svg)](https://imagelayers.io/?images=plugins/drone-lambda:latest 'Get your own badge on imagelayers.io')

Drone plugin for deploying to AWS Lambda

## Usage

```sh
./drone-lambda <<EOF
{
    "repo": {
        "clone_url": "git://github.com/drone/drone",
        "full_name": "drone/drone"
    },
    "build": {
        "event": "push",
        "branch": "master",
        "commit": "436b7a6e2abaddfd35740527353e78a227ddcb2c",
        "ref": "refs/heads/master"
    },
    "workspace": {
        "root": "/drone/src",
        "path": "/drone/src/github.com/drone/drone"
    },
    "vargs": {
    }
}
EOF
```

## Docker

Build the Docker container using `make`:

```sh
make deps build
docker build --rm=true -t plugins/drone-lambda .
```

### Example

```sh
docker run -i plugins/drone-lambda <<EOF
{
    "repo": {
        "clone_url": "git://github.com/drone/drone",
        "full_name": "drone/drone"
    },
    "build": {
        "event": "push",
        "branch": "master",
        "commit": "436b7a6e2abaddfd35740527353e78a227ddcb2c",
        "ref": "refs/heads/master"
    },
    "workspace": {
        "root": "/drone/src",
        "path": "/drone/src/github.com/drone/drone"
    },
    "vargs": {
    }
}
EOF
```
