FROM golang:1.21.3-alpine

# Create directory for our app inside the container
WORKDIR /app

# Prepare dependencies
COPY go.mod ./
COPY go.sum ./
RUN go mod download

# Copy code /to the container image.
COPY . ./

# Build the binary and call it "docker-ssi-service"
RUN go build -tags jwx_es256k -o /did-dht ./cmd

EXPOSE 8305

CMD [ "/did-dht" ]