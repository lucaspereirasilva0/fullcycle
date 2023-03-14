FROM golang AS buider
WORKDIR /app
COPY go.mod ./
RUN go mod download
COPY *.go ./
RUN go build -o hello-world.go

FROM scratch
WORKDIR /app
COPY --from=buider /app /app
CMD [ "/app/hello-world.go" ]