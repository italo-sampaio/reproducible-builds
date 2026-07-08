# rskj VETIVER-9.0.4

* Source: https://github.com/italo-sampaio/rskj
* Tag: `VETIVER-9.0.4`

## Build

```
$ docker build -t rskj/9.0.4-vetiver .
```

## Verify

Run the following command to verify the sha256sum of the built artifacts matches the expected values:

```
$ docker run --rm rskj/9.0.4-vetiver sh -c 'sha256sum * | grep -v javadoc.jar'
72ce93a39bb13629634d1cb500626a51b2c2d29bde59c8f8eb55db7fcaf54aac  rskj-core-9.0.4-VETIVER-all.jar
fb3b9b00b283908c9ac2a074d398c0b398c4fb925df4448f1e52fd1736206ca5  rskj-core-9.0.4-VETIVER-sources.jar
a4fa6b0595c4dc845b4272bda7c62cca7f8b20c9bb36a59f59622187635d13d2  rskj-core-9.0.4-VETIVER.jar
6be9848dcbabb7ee458ebe205438717f8252a76c4143299d6ee2baf32841ffd6  rskj-core-9.0.4-VETIVER.module
df341067d744cfb42e31be8b8301f8af608d83492bd7282b51af144e47152fce  rskj-core-9.0.4-VETIVER.pom
```

## (Optional) Run RSK Node
```
$ docker run -d rskj/9.0.4-vetiver
```

## (Optional) Extract JAR from image

```
$ cid=$(docker run -d rskj/9.0.4-vetiver /bin/true)
$ docker cp "$cid":/home/rsk/ ./libs/
$ docker rm "$cid"
```
