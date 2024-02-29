# Roon Docker Image

![docker publish workflow](https://github.com/HasseJohansen/roon-docker-image/actions/workflows/docker-publish.yml/badge.svg)

A Docker image for roon.

```
docker pull ghcr.io/HasseJohansen/roon:latest
```

```
docker run -d \
  --network host
  --name=roon-server \
  -v </path/to/config/>:/var/roon \
  -v </path/to/music/library>:/music \
  --restart unless-stopped \
  ghcr.io/HasseJohansen/roon:latest
```


This is based on jmmaloney4's great work. I just needed to see if I could autobuild new version when roon publishes new versions

## Kubernetes Helm Chart
See [github.com/jmmaloney4/charts](https://github.com/jmmaloney4/charts) for a helm chart. 

### Releasing

See the [Release Notes](https://community.roonlabs.com/t/roon-2-0-current-production-versions/213416) for the latest.

The pipelin in this repo will check each day if there is a new new roon version released from the above page (fingers crossed they don't change the layout too much) and build a new image
