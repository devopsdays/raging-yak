FROM mcr.microsoft.com/devcontainers/base:alpine-3.20 AS base

# install hugo
FROM base AS hugo
WORKDIR /tmp/hugo
ARG TARGETARCH
ARG HUGO_VERSION=0.121.1
RUN wget -O "hugo.tar.gz" "https://github.com/gohugoio/hugo/releases/download/v${HUGO_VERSION}/hugo_extended_${HUGO_VERSION}_linux-${TARGETARCH}.tar.gz"
RUN tar -xf "hugo.tar.gz" hugo -C /usr/bin

RUN apk add --no-cache libc6-compat libstdc++

# install Embedded Dart SASS.
RUN apk add dart-sass --repository=http://dl-cdn.alpinelinux.org/alpine/edge/testing/
RUN apk add --no-cache dart-sass