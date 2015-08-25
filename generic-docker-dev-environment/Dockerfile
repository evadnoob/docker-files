FROM debian:jessie
MAINTAINER david boon <davidb@porch.com>

ENV RUST_VERSION=nightly

RUN echo 'deb http://apt.postgresql.org/pub/repos/apt/ jessie-pgdg main' 9.4 > /etc/apt/sources.list.d/pgdg.list
RUN apt-get update

RUN DEBIAN_FRONTEND=noninteractive apt-get install -y --force-yes --no-install-recommends \
    build-essential \
    ca-certificates \
    ruby-full \
    curl \
    git \
    autoconf \
    bison \
    build-essential \
    libreadline6-dev \
    python-software-properties \
    software-properties-common \
    libpq-dev \
    postgresql-client-9.4 \
    libssl-dev && \
  curl -sO https://static.rust-lang.org/dist/rust-$RUST_VERSION-x86_64-unknown-linux-gnu.tar.gz && \
  tar -xzf rust-$RUST_VERSION-x86_64-unknown-linux-gnu.tar.gz && \
  ./rust-$RUST_VERSION-x86_64-unknown-linux-gnu/install.sh --without=rust-docs && \
  DEBIAN_FRONTEND=noninteractive apt-get autoremove -y && \
  rm -rf \
    rust-$RUST_VERSION-x86_64-unknown-linux-gnu \
    rust-$RUST_VERSION-x86_64-unknown-linux-gnu.tar.gz \
    /var/lib/apt/lists/* \
    /tmp/* \
    /var/tmp/* && \
  mkdir /source

CMD ["bash"]


