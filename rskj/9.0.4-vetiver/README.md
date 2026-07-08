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
9c5b42b05f6b111ff632c08f5901f91441fa6c1cffe612124757baf953e1bdb2  rskj-core-9.0.4-VETIVER-all.jar
fb3b9b00b283908c9ac2a074d398c0b398c4fb925df4448f1e52fd1736206ca5  rskj-core-9.0.4-VETIVER-sources.jar
1596b3a92ef822eab95ce29b26f3ce8b6e8f64a5460da281196ffba2af9faf89  rskj-core-9.0.4-VETIVER.jar
00192759fea48e28e017abb048b12f27d9591ec2693e1eb1ca05ffbc927a5daa  rskj-core-9.0.4-VETIVER.module
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
