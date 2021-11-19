FROM ubuntu:21.10

ENV LC_ALL C
ENV DEBIAN_FRONTEND noninteractive

RUN apt update --yes && \
    apt install --no-install-recommends --yes \
    vim less iputils-ping net-tools \
    python3-dev python3-pip

# use --user ?
RUN pip3 install --no-cache-dir --quiet --upgrade \
    virtualenv \
    tensorflow-federated-nightly \
    nest-asyncio
RUN pip3 freeze


# COPY ./worker/code /app

EXPOSE 22
EXPOSE 8000

CMD ["python3", "/app/main.py"]
