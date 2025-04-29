FROM eclipse-temurin:17

RUN  apt-get update -y \
     && apt-get upgrade -y \
	 && apt-get install -y lsof git git-lfs curl ca-certificates openssl tar sqlite3 fontconfig tzdata libstdc++6 \
	 && apt-get clean \
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
	 && useradd -u 2200 -m runner

USER  2200
ENV   HOME=/home/runner
ENV   USER=runner

WORKDIR /home/runner

CMD [ "/bin/sh", "__entrypoint_server.sh" ]
