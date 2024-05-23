# docker build -t hackuntu:1.0 .

FROM --platform=linux/amd64 ubuntu:22.04

# set env
ENV LC_CTYPE C.UTF-8
ENV DEBIAN_FRONTEND=noninteractive

# install packages
RUN apt update && \
apt install -y zsh file build-essential jq strace unzip curl wget gcc dnsutils netcat net-tools vim gdb gdb-multiarch python3 python3-pip python3-dev git make

# directory to drop tools at
RUN mkdir /tools

# zsh plugins
RUN cd /tools && \
wget https://github.com/zsh-users/zsh-syntax-highlighting/archive/refs/tags/0.8.0.tar.gz && \
tar xzf 0.8.0.tar.gz
RUN echo "source /tools/zsh-syntax-highlighting-0.8.0/zsh-syntax-highlighting.zsh" >> /root/.zshrc

# install aws cli
RUN cd /tools && \
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip" && \
unzip awscliv2.zip && \
./aws/install

