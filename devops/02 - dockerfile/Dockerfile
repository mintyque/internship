#FROM golang:1.15
#WORKDIR /usr/src/app
#COPY main.go .
#COPY go.mod .
#COPY .env .
#RUN go get -d github.com/joho/godotenv 
#RUN CGO_ENABLED=0 GOOS=linux go build -o simple-webpage .
#CMD ["./simple-webpage"]

FROM golang:alpine
WORKDIR /usr/src/app
COPY main.go .
COPY go.mod .
ARG PORT
RUN echo $PORT
RUN go get -d github.com/joho/godotenv
RUN CGO_ENABLED=0 GOOS=linux go build -o simple-webpage .

FROM alpine
WORKDIR /app/
COPY --from=0 /usr/src/app/ /app/
CMD ["./simple-webpage"]
