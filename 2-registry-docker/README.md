# Registry (private hub) Docker

ref https://docs.docker.com/registry/deploying/

ref https://xuanthulab.net/tao-kho-chua-registry-rieng-de-chua-cac-image-docker.html

```
docker run -d -p 5000:5000 -v /home/registry:/var/lib/registry registry:2.7
```