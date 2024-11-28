ARG NODE_VERSION=18
FROM node:$NODE_VERSION

ARG AWS_CLI_VERSION=2.22.5
RUN echo "AWS CLI Version: $AWS_CLI_VERSION"
RUN apt-get update && \
    apt-get install -y \
        unzip \
        curl \
    && apt-get clean \
    && curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64-$AWS_CLI_VERSION.zip" -o "awscliv2.zip" \
    && unzip awscliv2.zip \
    && ./aws/install \
    && rm -rf \
        awscliv2.zip \
    && apt-get -y purge curl \
    && apt-get -y purge unzip 

RUN npm install -g ipfs-car@1.2.0

RUN aws --version
RUN node --version
RUN npm --version
RUN npm list -g ipfs-car

CMD ["/bin/bash"]
