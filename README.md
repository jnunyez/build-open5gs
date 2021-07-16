# build-open5gs

This repo contains the generation of the [open5gs](https://github.com/open5gs/open5gs) image, hosting an open-source SoA 5G and 4G Core implementation. It can be considered as a convergent core netowrk. 

## WorkFlow

The image is built inside vagrant Fedora VM using buildah. Once the two images are built they are pushed to a registry. The image pushed in a registry will be consumed by k8s.

## Quickstart


1. Deploy and log in vagrant VM:

   ```
   vagrant up
   vagrant ssh
   cd /vagrant
   ```

2. Build the open5gs and webui image:

   ```
   build-open5gs #TBA generation and diameter patches 
   build-webui
   ```

3. Push webui container to registry (in this case an insecure registry):

   ```
   load-webui
   ```

4. Deploy on your preferred container cluster platform. See this [repo](https://github.com/jnunyez/kindk8s-open5gs) for deploying open5gs in k8s.

## ToDo

- Add open5gs image generator in addition to webui image generator.
