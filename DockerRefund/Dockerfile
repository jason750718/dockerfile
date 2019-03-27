FROM golang:1.12.0-alpine
WORKDIR /RefundServer
ADD /RefundServer /RefundServer
RUN go get -d -v ./...
RUN go install -v ./...
RUN go get github.com/go-sql-driver/mysql
RUN go get github.com/julienschmidt/httprouter
RUN cd /RefundServer && go build
EXPOSE 8081
ENTRYPOINT ./RefundServer
