# use ubuntu image
FROM golang

COPY ./ /usr/local/go/src/github.com/stellar/go
WORKDIR /usr/local/go/src/github.com/stellar/go

# build
RUN curl https://glide.sh/get | sh
RUN glide install

# RUN ls -laR /usr/local/go

RUN go install github.com/stellar/go/services/horizon

# expose ports
EXPOSE 8000

CMD ["/usr/local/horizon/config/init-horizon.sh"]
