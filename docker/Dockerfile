ARG GO_VERSION=latest
ARG ROCKY_VERSION=9.3-minimal

FROM golang:${ROCKY_VERSION} as base
WORKDIR /work
COPY ./app /work
RUN go build -o /bin/app /work

FROM rockylinux:${ROCKY_VERSION}
COPY --from=build /bin/app /bin/app
USER golang
ENTRYPOINT ["/bin/app"]
