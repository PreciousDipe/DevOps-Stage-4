FROM golang:1.21-alpine
WORKDIR /app
COPY go.mod go.sum ./
RUN go mod download
COPY . .
RUN go build -o auth-api
EXPOSE 8081
ENV AUTH_API_PORT=8081
CMD ["./auth-api"]
