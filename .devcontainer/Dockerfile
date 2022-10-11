FROM ubuntu:22.04

# non interactive frontend for locales
ENV DEBIAN_FRONTEND=noninteractive

# installing texlive and utils
RUN apt-get update && \
    apt-get -y install --no-install-recommends pandoc texlive-full biber latexmk make git procps locales curl && \
    rm -rf /var/lib/apt/lists/*

# generating locales
RUN sed -i -e 's/# pl_PL.UTF-8 UTF-8/pl_PL.UTF-8 UTF-8/' /etc/locale.gen && \
    dpkg-reconfigure --frontend=noninteractive locales && \
    update-locale LANG=pl_PL.UTF-8
ENV LANGUAGE=pl_PL.UTF-8 LANG=pl_PL.UTF-8 LC_ALL=pl_PL.UTF-8
