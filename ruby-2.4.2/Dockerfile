FROM ruby:2.4.2

ENV TERRAFORM_VERSION 0.11.7

RUN apt-get update &&\
    apt-get install --no-install-recommends -y unzip &&\
    apt-get autoremove -y && rm -rf /var/lib/apt/lists/*

RUN wget https://releases.hashicorp.com/terraform/${TERRAFORM_VERSION}/terraform_${TERRAFORM_VERSION}_linux_amd64.zip &&\
    unzip terraform_${TERRAFORM_VERSION}_linux_amd64.zip &&\
    mv terraform /var/lib &&\
    ln -s /var/lib/terraform /usr/local/bin/terraform &&\
    rm -rf terraform_${TERRAFORM_VERSION}}_linux_amd64.zip
