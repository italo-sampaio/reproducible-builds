# rskj PILOT-9.0.3

* Source: https://github.com/italo-sampaio/rskj
* Tag: `PILOT-9.0.3`

## Build

```
$ docker build -t rskj/9.1.0-snapshot .
```

## Verify

Run the following command to verify the sha256sum of the built artifacts matches the expected values:

```
$ docker run --rm rskj/9.1.0-snapshot sh -c 'sha256sum * | grep -v javadoc.jar'
abccbabafe50e5ab710d1d525ebb76e1eaff1c103673ef3972aa5978c8ec4a8d  rskj-core-9.1.0-SNAPSHOT-all.jar
6e575b9905e08872a550161354bbdf6e787a717daad889fb38f8e1cefa96d3b6  rskj-core-9.1.0-SNAPSHOT-sources.jar
744c7537da32abb7b286fad5e149107faf8d282a7de8c3e2d1cd7085e7c8ad90  rskj-core-9.1.0-SNAPSHOT.jar
dc70a2348987a90a1ed7f6ffc59fb82ebd08a8c75fb3ac54a33a132bc731e0d0  rskj-core-9.1.0-SNAPSHOT.module
2aa8cafa9e07bce0898e56f893fe5d358f2ab990dfedc17340c118bbd0a60903  rskj-core-9.1.0-SNAPSHOT.pom
```

## (Optional) Run RSK Node
```
$ docker run -d rskj/9.1.0-snapshot
```

## (Optional) Extract JAR from image

```
$ cid=$(docker run -d rskj/9.1.0-snapshot /bin/true)
$ docker cp "$cid":/home/rsk/ ./libs/
$ docker rm "$cid"
```
