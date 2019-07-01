FROM circleci/php:7.2-cli-node

USER root

RUN docker-php-ext-install bcmath && \
    sudo npm install --global babel-cli && \
    sudo npm install --global gulp-cli && \
    sudo npm install --global bower && \
    sudo apt-get install -y build-essential libpng-dev

USER circleci
