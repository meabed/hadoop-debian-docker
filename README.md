#Apache Hadoop 2.5.1 Docker image


# Build the image

If you'd like to try directly from the Dockerfile you can build the image as:

```
docker build  -t  meabed/hadoop-debian:latest .
```
# Pull the image

The image is also released as an official Docker image from Docker's automated build repository - you can always pull or refer the image when launching containers.

```
docker pull meabed/hadoop-debian:latest
```

# Start a container

In order to use the Docker image you have just build or pulled use:

```
docker run -i -t meabed/hadoop-debian:latest /etc/bootstrap.sh -bash
```

## Testing

You can run one of the stock examples:

```
cd $HADOOP_PREFIX
# run the mapreduce
bin/hadoop jar share/hadoop/mapreduce/hadoop-mapreduce-examples-2.5.0.jar grep input output 'dfs[a-z.]+'

# check the output
bin/hdfs dfs -cat output/*
```

## Hadoop native libraries, build, Bintray, etc

The Hadoop build process is no easy task - requires lots of libraries and their right version, protobuf, etc and takes some time - we have simplified all these, made the build and released a 64b version of Hadoop nativelibs on this [Bintray repo](https://bintray.com/meabed/hadoop-debian/hadoop-native-64-2.5.1/0.0.1/view/files). Enjoy.

## Automate everything

As mentioned previousely, a Docker file was created and released in the official [Docker repository](https://registry.hub.docker.com/u/meabed/hadoop-debian/)
