FROM mongo:3
MAINTAINER Alexander Lukyanchikov <sqshq@sqshq.com>

ADD init.sh /init.sh
ADD ./dump /


RUN \
 chmod +x /init.sh && \
 export http_proxy=http://10.209.0.13:3128 && \
 export https_proxy=http://10.209.0.13:3128 && \
 export HTTP_PROXY=http://10.209.0.13:3128 && \
 export HTTPS_PROXY=http://10.209.0.13:3128 && \
 apt-get update && apt-get dist-upgrade -y && \
 apt-get install psmisc -y -q && \
 apt-get autoremove -y && apt-get clean && \
 rm -rf /var/cache/* && rm -rf /var/lib/apt/lists/*

ENTRYPOINT ["/init.sh"]