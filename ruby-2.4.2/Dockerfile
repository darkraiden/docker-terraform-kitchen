FROM ruby:2.4.2

ENV TERRAFORM_VERSION 0.11.7
ENV BUILD_PACKAGES unzip
ENV GEM_PACKAGES bundler\
    aws-sdk:3.0.1\
    awspec:1.4.0\
    kitchen-terraform:3.1\
    kitchen-verifier-awspec:0.1.1\
    rhcl:0.1.0

# Install build packages
RUN apt-get update &&\
    apt-get install --no-install-recommends -y ${BUILD_PACKAGES} &&\
    apt-get autoremove -y && rm -rf /var/lib/apt/lists/*

# Download and Install terraform
RUN wget https://releases.hashicorp.com/terraform/${TERRAFORM_VERSION}/terraform_${TERRAFORM_VERSION}_linux_amd64.zip &&\
    unzip terraform_${TERRAFORM_VERSION}_linux_amd64.zip &&\
    mv terraform /var/lib &&\
    ln -s /var/lib/terraform /usr/local/bin/terraform &&\
    rm -rf terraform_${TERRAFORM_VERSION}}_linux_amd64.zip

# Remove build packages
RUN apt-get remove --purge --force-yes -y ${BUILD_PACKAGES} && rm -rf /var/lib/apt/lists/*

# Install gems for kitchen and awspec
RUN gem install ${GEM_PACKAGES}
