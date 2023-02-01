FROM ghcr.io/graalvm/native-image:22.3.1 AS builder

WORKDIR /app

COPY HelloWorld.java .

RUN javac HelloWorld.java
RUN native-image HelloWorld

FROM ubuntu:23.04 as runner

WORKDIR /

COPY --from=builder /app/helloworld .

CMD ./helloworld