# log-to-elk-microservice

This is a basic microservice that sends data to a logstash node.

It has a rest endpoint: `/hello` that can be accessed with the following curl:

```bash
curl localhost:8080/hello
```

With each get to the microservice, it gathers metrics and sends a `DEBUG` and an `INFO` trace per call.

## Docker hub

This microservice has been uploaded to [hub.docker.com](https://hub.docker.com/u/rpardom). It can be pulled as a docker image with:

```bash
docker pull rpardom/log-to-elk-microservice
```

## Quarkus

This project uses Quarkus, the Supersonic Subatomic Java Framework.

If you want to learn more about Quarkus, please visit its website: https://quarkus.io/ .

## Running the application in dev mode

You can run your application in dev mode that enables live coding using:
```
mvn quarkus:dev
```

## Packaging and running the application

The application can be packaged using `./mvnw package`.
It produces the `log-to-elk-microservice-1.0.0-SNAPSHOT-runner.jar` file in the `/target` directory.
Be aware that it’s not an _über-jar_ as the dependencies are copied into the `target/lib` directory.

The application is now runnable using `java -jar target/log-to-elk-microservice-1.0.0-SNAPSHOT-runner.jar`.

## Creating a native executable

You can create a native executable using: `./mvnw package -Pnative`.

Or, if you don't have GraalVM installed, you can run the native executable build in a container using: `./mvnw package -Pnative -Dquarkus.native.container-build=true`.

You can then execute your native executable with: `./target/log-to-elk-microservice-1.0.0-SNAPSHOT-runner`

If you want to learn more about building native executables, please consult https://quarkus.io/guides/building-native-image-guide.