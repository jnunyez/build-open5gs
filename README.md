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

2. Build the image:
	* Building open5gs base image:
   
   ```
   build-open5gs
   ```
   
   * Building web user interface base  image:

   ```
   build-webui
   ```

3. Push image (webui or open5gs) container to registry (in this case an insecure registry).

   * Push open5gs base image:
   ```
   load-image open5gs 
   ```

   * Push webui base image:

   ```
   load-image webui
   ```


4. Deploy on your preferred container cluster platform. See this [repo](https://github.com/jnunyez/kindk8s-open5gs) for deploying open5gs in k8s.


