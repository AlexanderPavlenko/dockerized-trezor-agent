FROM python:3-alpine

RUN apk update && apk add --virtual .build-deps gcc musl-dev git
RUN pip3 install Cython

RUN git clone --depth 1 --branch AlexanderPavlenko-trezor-without-hidapi \
    https://github.com/AlexanderPavlenko/trezor-agent.git /src
RUN pip3 install -e /src/agents/trezor

RUN apk add openssh socat \
  && apk --purge del .build-deps \
  && rm -rf /src/.git

CMD ["trezor-agent"]