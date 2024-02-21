FROM debian:stable-slim

LABEL maintainer='clerouxfr@me.com'

VOLUME ["/data"]

COPY student_age.py /

RUN apt-get update -y && \
    apt-get install -y --no-install-recommends \
        python3 \
        libsasl2-dev \
        libldap2-dev \
        libssl-dev \
        python3-pip \
        python3-venv \
        vim && \
    rm -rf /var/lib/apt/lists/* && \
    apt-get clean &&\
    python3 -m venv /tmp/venv &&\
    /tmp/venv/bin/python3 -m pip install flask==1.1.2 flask_httpauth==4.1.0 pip python-dotenv==0.14.0

EXPOSE 5000

CMD ["python3", "./student_age.py"]