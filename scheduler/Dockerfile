FROM golang:1.16.3 as build
WORKDIR /src
COPY . ./
RUN go build -o scheduler main.go


FROM ubuntu:21.04@sha256:be154cc2b1211a9f98f4d708f4266650c9129784d0485d4507d9b0fa05d928b6

COPY --from=build /src/scheduler /usr/local/bin/scheduler

ENTRYPOINT /usr/local/bin/scheduler
