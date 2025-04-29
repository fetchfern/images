FROM amazoncorretto:11

RUN  yum update -y \
     && yum install -y git lsof curl ca-certificates openssl tar sqlite fontconfig freetype tzdata iproute libstdc++ \
	 && yum clean all \
	 && rm -rf /var/cache/yum \
     && rm -f /usr/bin/fallocate \
          /usr/bin/truncate  \
          /usr/bin/tail      \
          /usr/bin/head      \
          /usr/bin/dd        \
          /usr/bin/mount     \
          /usr/bin/umount    \
          /usr/bin/mkfifo    \
          /usr/bin/yes       \
          /usr/bin/shred     \
          /sbin/mount        \
          /sbin/umount       \
          /sbin/mount        \
          /bin/mount         \
          /bin/umount        \
	 && adduser -u 2200 -m runner

USER  2200
ENV   HOME=/home/runner
ENV   USER=runner

WORKDIR /home/runner

CMD [ "/bin/sh", "__entrypoint_server.sh" ]
