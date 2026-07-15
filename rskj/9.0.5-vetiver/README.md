# rskj VETIVER-9.0.5

* Source: https://github.com/italo-sampaio/rskj
* Tag: `VETIVER-9.0.5`

## Build

```
$ docker build -t rskj/9.0.5-vetiver .
```

## Verify

Run the following command to verify the sha256sum of the built artifacts matches the expected values:

```
$ docker run --rm rskj/9.0.5-vetiver sh -c 'sha256sum * | grep -v javadoc.jar'
7011afe7f2079505a10c446acb374af796cd5838e6c3c0a1a4ed66bb5ec31348  rskj-core-9.0.5-VETIVER-all.jar
dbfe81146d08c64573425e3fcf54971d6b696ea2c3fe4385bf6a203b9e61ea07  rskj-core-9.0.5-VETIVER-sources.jar
3d4ab6811dfcf9a9b227899d78dfa2f237f9cd92f2a735069a2703f149bf2132  rskj-core-9.0.5-VETIVER.jar
cfe8b78a4db0494c6a0f16c159a8daf0a46d5ab4e4ab0dd387e4bce19318695d  rskj-core-9.0.5-VETIVER.module
f394d529b4f6f9fae190c5200c47f317693e05f9bbb4822b2286e7d72ce5c057  rskj-core-9.0.5-VETIVER.pom
```

## (Optional) Run RSK Node
```
$ docker run -d rskj/9.0.5-vetiver
```

## (Optional) Extract JAR from image

```
$ cid=$(docker run -d rskj/9.0.5-vetiver /bin/true)
$ docker cp "$cid":/home/rsk/ ./libs/
$ docker rm "$cid"
```
