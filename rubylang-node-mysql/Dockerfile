FROM rubylang/ruby:2.6-bionic

# Install Requirement packages for installing node and yarn
RUN apt-get update \
  && apt-get install -y curl gnupg \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/*

RUN curl -sL https://deb.nodesource.com/setup_11.x | bash - \
  && curl -sL https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add - \
  && echo "deb https://dl.yarnpkg.com/debian/ stable main" | tee /etc/apt/sources.list.d/yarn.list \
  && apt-get update \
  && apt-get install -y build-essential mariadb-client libmariadbclient-dev libcurl4 nodejs yarn tzdata \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/*

RUN curl -sL https://www.ubuntulinux.jp/ubuntu-ja-archive-keyring.gpg | apt-key add - \
  && curl -sL https://www.ubuntulinux.jp/ubuntu-jp-ppa-keyring.gpg | apt-key add - \
  && curl https://www.ubuntulinux.jp/sources.list.d/bionic.list -o /etc/apt/sources.list.d/ubuntu-ja.list \
  && curl -O https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb \
  && apt update \
  && apt install -y fonts-ipafont \
  && apt install -y ./google-chrome-stable_current_amd64.deb \
  && rm ./google-chrome-stable_current_amd64.deb \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/*

WORKDIR /usr/src/app
