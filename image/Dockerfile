FROM ubuntu:noble-20250415.1
ENV DEBIAN_FRONTEND noninteractive
RUN apt-get -qq update
RUN apt-get install -y \
    pandoc python3 python3-dev python3-pip python3-venv \
    git texlive-latex-base texlive-latex-extra texlive-xetex cm-super dvipng

# setup python virtual environment
ENV VIRTUAL_ENV=/opt/venv
RUN python3 -m venv $VIRTUAL_ENV
ENV PATH="$VIRTUAL_ENV/bin:$PATH"

# install python packages
#  upgrade pip first
RUN pip3 install --upgrade pip
#  install and upgrade analysis-specific packages next
COPY image/requirements /tmp/requirements
RUN pip3 install -r /tmp/requirements

RUN mkdir -p /analysis
WORKDIR /analysis