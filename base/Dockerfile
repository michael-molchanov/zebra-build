FROM drush/drush:8-alpine

LABEL maintainer "Michael Molchanov <mmolchanov@adyax.com>"

USER root

# SSH config.
RUN mkdir -p /root/.ssh
ADD config/ssh /root/.ssh/config
RUN chmod 600 /root/.ssh/config

# Install docman.
RUN apk add --update --no-cache ruby \
  && rm -rf /var/cache/apk/* \
  && gem install --no-ri --no-rdoc specific_install \
  && gem specific_install https://github.com/Adyax/docman.git develop
