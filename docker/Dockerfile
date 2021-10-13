FROM octahub.8lab.cn:5000/base/ubuntu:18.04

COPY sources.list /etc/apt/sources.list
RUN useradd -u 1000 action -s /bin/bash \
    && ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime \
    && apt update && apt install -y tzdata dnsutils 

COPY --chown=action testAction /usr/bin/testAction
COPY --chown=action entrypoint.sh /usr/bin/entrypoint.sh

USER action

ENTRYPOINT ["entrypoint.sh"]
