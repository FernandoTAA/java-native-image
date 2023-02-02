FROM ghcr.io/graalvm/native-image:22.3.1 AS builder

WORKDIR /app

COPY mvnw .
COPY .mvn .mvn
COPY pom.xml .
COPY src src

RUN ./mvnw clean package

FROM ubuntu:23.04 as runner

WORKDIR /

COPY --from=builder /app/target/maven-project .

CMD ./maven-project