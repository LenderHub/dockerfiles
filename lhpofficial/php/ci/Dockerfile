FROM circleci/php:7.2-cli-node

USER root

RUN apt update \
    && apt install python-pip \
    && sudo -u circleci pip install awscli --upgrade --user \
    && docker-php-ext-install bcmath \
    && echo 'export PATH=~/.local/bin:$PATH' >> /home/circleci/.bashrc \
    && docker-php-ext-install bcmath \
    && npm install --global babel-cli \
    && npm install --global gulp-cli \
    && npm install --global bower \
    && apt-get install -y build-essential libpng-dev

USER circleci
