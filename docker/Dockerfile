ARG GO_VERSION=latest
ARG ROCKY_VERSION=9.3-minimal

FROM golang:${GO_VERSION} as base
WORKDIR /work
COPY ./app /work
RUN go build -o /bin/app /work

FROM rockylinux:${ROCKY_VERSION}
ARG USERNAME=golang
ARG GROUPNAME=golang
COPY --from=base /bin/app /bin/app
RUN groupadd -g 1000 ${GROUPNAME} && \
    useradd -m -s /bin/bash -u 1000 -g ${GROUPNAME} ${USERNAME}
USER $USERNAME
ENTRYPOINT ["/bin/app"]
