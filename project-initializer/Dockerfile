FROM golang:1.11.0-alpine3.8 as build
RUN apk add --no-cache libc-dev glide git
RUN go get github.com/golang/protobuf/proto
RUN go get github.com/googleapis/gnostic/OpenAPIv2
COPY Gopkg.* glide.* build* *.go /go/src/github.com/harbur/project-initializer/
COPY api /go/src/github.com/harbur/project-initializer/api/
COPY clientset /go/src/github.com/harbur/project-initializer/clientset/
WORKDIR /go/src/github.com/harbur/project-initializer
RUN glide install
RUN ./build


FROM scratch
COPY --from=build /go/src/github.com/harbur/project-initializer/project-initializer /project-initializer
ENTRYPOINT ["/project-initializer"]
