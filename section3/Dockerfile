# Use an existing docker image as a base
FROM alpine

# Download and install a dependency in the alpine container and create a new image snapshot with redis. Then, delete the old alpine container
RUN apk add --update gcc redis

# Tell this image what to do when it starts as a container
CMD ["redis-server"]

# Example build log:

# Sending build context to Docker daemon   2.56kB
# Step 1/3 : FROM alpine                            // Start new image with base alpine linux OS image
# latest: Pulling from library/alpine
# df20fa9351a1: Pull complete
# Digest: sha256:185518070891758909c9f839cf4ca393ee977ac378609f700f60a771a2dfe321
# Status: Downloaded newer image for alpine:latest
#  ---> a24bb4013296
# Step 2/3 : RUN apk add --update redis
#  ---> Running in 8b6c27947cd9 // Take the RUN command and execute it in container 8b6c27947cd9, then take that container and create a new image 8845601a62bd
# fetch http://dl-cdn.alpinelinux.org/alpine/v3.12/main/x86_64/APKINDEX.tar.gz
# fetch http://dl-cdn.alpinelinux.org/alpine/v3.12/community/x86_64/APKINDEX.tar.gz
# (1/1) Installing redis (5.0.9-r0)
# Executing redis-5.0.9-r0.pre-install
# Executing redis-5.0.9-r0.post-install
# Executing busybox-1.31.1-r16.trigger
# OK: 7 MiB in 15 packages
# Removing intermediate container 8b6c27947cd9
#  ---> 8845601a62bd
# Step 3/3 : CMD ["redis-server"]                   // Take image 8845601a62bd, create a container f96875539e49, and set its startup command and return a final image 4949f44c55c1
#  ---> Running in f96875539e49
# Removing intermediate container f96875539e49
#  ---> 4949f44c55c1
# Successfully built 4949f44c55c1                   // The final image

# Example build log using cache:

# Sending build context to Docker daemon  2.048kB
# Step 1/3 : FROM alpine
#  ---> a24bb4013296
# Step 2/3 : RUN apk add --update redis // Found built image in cache, so just using it
#  ---> Using cache
#  ---> 53d3bb5bfc74
# Step 3/3 : CMD ["redis-server"]      // Found built image in cache, so just using it
#  ---> Using cache
#  ---> 3d6937c465e8
# Successfully built 3d6937c465e8
