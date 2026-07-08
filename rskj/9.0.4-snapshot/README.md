# rskj VETIVER-9.0.4-rc

* Source: https://github.com/italo-sampaio/rskj
* Tag: `VETIVER-9.0.4-rc`

## Build

```
$ docker build -t rskj/9.0.4-snapshot .
```

## Verify

Run the following command to verify the sha256sum of the built artifacts matches the expected values:

```
$ docker run --rm rskj/9.0.4-snapshot sh -c 'sha256sum * | grep -v javadoc.jar'
ccb7090cb0dc4a67639ddfb0aace835bae075fd84c5b30997562c33567bb302b  rskj-core-9.0.4-SNAPSHOT-all.jar
db7282cc28fd1c3d729ab2d1080a7054ccce54ebd17d23274e023c2320e08118  rskj-core-9.0.4-SNAPSHOT-sources.jar
fac8f806b0049daa860007990758ee677eff7899351f1c7e495998542770d025  rskj-core-9.0.4-SNAPSHOT.jar
46dc58d14b791bdcc69de858a4b64fb64eccb7446bfb2fb159a90ec825f0c82c  rskj-core-9.0.4-SNAPSHOT.module
0c5255ab8ed9e6f3d8c8831b13ab4e4b2a362b091fa4126f881369dd83396a3a  rskj-core-9.0.4-SNAPSHOT.pom
```

## (Optional) Run RSK Node
```
$ docker run -d rskj/9.0.4-snapshot
```

## (Optional) Extract JAR from image

```
$ cid=$(docker run -d rskj/9.0.4-snapshot /bin/true)
$ docker cp "$cid":/home/rsk/ ./libs/
$ docker rm "$cid"
```
