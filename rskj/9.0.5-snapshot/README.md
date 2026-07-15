# rskj VETIVER-9.0.5-rc

* Source: https://github.com/italo-sampaio/rskj
* Tag: `VETIVER-9.0.5-rc`

## Build

```
$ docker build -t rskj/9.0.5-snapshot .
```

## Verify

Run the following command to verify the sha256sum of the built artifacts matches the expected values:

```
$ docker run --rm rskj/9.0.5-snapshot sh -c 'sha256sum * | grep -v javadoc.jar'
2325feff777c284a55ee5de2abee06552dff751e271eff2491b8e4f935a35612  rskj-core-9.0.5-SNAPSHOT-all.jar
6b7640054faf1f0678fad9280f792f14a47d7e03fe9e4b7290e0f57b4e2cf7f8  rskj-core-9.0.5-SNAPSHOT-sources.jar
a32e16ef0e114c217d3874904443a98e510014919f1617e51beacccd77e77448  rskj-core-9.0.5-SNAPSHOT.jar
d46ba28597a16f43abf0dbcac960ccac93bfdc0654755f78fd545e9a3ed0d906  rskj-core-9.0.5-SNAPSHOT.module
6ff96bc6fa615a66b766f2df3a6f690e9b6c0886e84f2643bad74eb975b8b241  rskj-core-9.0.5-SNAPSHOT.pom
```

## (Optional) Run RSK Node
```
$ docker run -d rskj/9.0.5-snapshot
```

## (Optional) Extract JAR from image

```
$ cid=$(docker run -d rskj/9.0.5-snapshot /bin/true)
$ docker cp "$cid":/home/rsk/ ./libs/
$ docker rm "$cid"
```
