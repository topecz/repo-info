## `logstash:latest`

```console
$ docker pull logstash@sha256:bb5c1add71a63b1a64165c17c2a360aa3e362b1d28f7e57a03a79ef1ab803ddf
```

-	Platforms:
	-	linux; amd64

### `logstash:latest` - linux; amd64

-	Docker Version: 1.12.1
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **210.7 MB (210683299 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:3bf46fa073e5a8d33ef8a4cbc037aba720a991c3e67d83ce4eee6c21733cd4c1`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["-e",""]`

```dockerfile
# Fri, 23 Sep 2016 18:08:50 GMT
ADD file:c6c23585ab140b0b320d4e99bc1b0eb544c9e96c24d90fec5e069a6d57d335ca in / 
# Fri, 23 Sep 2016 18:08:51 GMT
CMD ["/bin/bash"]
# Fri, 23 Sep 2016 18:25:17 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Fri, 23 Sep 2016 19:32:51 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Fri, 23 Sep 2016 19:37:42 GMT
RUN echo 'deb http://httpredir.debian.org/debian jessie-backports main' > /etc/apt/sources.list.d/jessie-backports.list
# Fri, 23 Sep 2016 19:37:42 GMT
ENV LANG=C.UTF-8
# Fri, 23 Sep 2016 19:37:43 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Fri, 23 Sep 2016 19:37:44 GMT
ENV JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64/jre
# Fri, 23 Sep 2016 19:37:44 GMT
ENV JAVA_VERSION=8u102
# Fri, 23 Sep 2016 19:37:44 GMT
ENV JAVA_DEBIAN_VERSION=8u102-b14.1-1~bpo8+1
# Fri, 23 Sep 2016 19:37:45 GMT
ENV CA_CERTIFICATES_JAVA_VERSION=20140324
# Fri, 23 Sep 2016 19:38:04 GMT
RUN set -x 	&& apt-get update 	&& apt-get install -y 		openjdk-8-jre-headless="$JAVA_DEBIAN_VERSION" 		ca-certificates-java="$CA_CERTIFICATES_JAVA_VERSION" 	&& rm -rf /var/lib/apt/lists/* 	&& [ "$JAVA_HOME" = "$(docker-java-home)" ]
# Fri, 23 Sep 2016 19:38:06 GMT
RUN /var/lib/dpkg/info/ca-certificates-java.postinst configure
# Sat, 24 Sep 2016 04:05:30 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		libzmq3 	&& rm -rf /var/lib/apt/lists/*
# Sat, 24 Sep 2016 04:05:31 GMT
RUN mkdir -p /usr/local/lib 	&& ln -s /usr/lib/*/libzmq.so.3 /usr/local/lib/libzmq.so
# Sat, 24 Sep 2016 04:05:32 GMT
ENV GOSU_VERSION=1.7
# Sat, 24 Sep 2016 04:05:38 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Sat, 24 Sep 2016 04:05:39 GMT
RUN apt-key adv --keyserver ha.pool.sks-keyservers.net --recv-keys 46095ACC8548582C1A2699A9D27D666CD88E42B4
# Sat, 24 Sep 2016 04:07:02 GMT
ENV LOGSTASH_MAJOR=2.4
# Sat, 24 Sep 2016 04:07:03 GMT
ENV LOGSTASH_VERSION=1:2.4.0-1
# Sat, 24 Sep 2016 04:07:03 GMT
RUN echo "deb http://packages.elastic.co/logstash/${LOGSTASH_MAJOR}/debian stable main" > /etc/apt/sources.list.d/logstash.list
# Sat, 24 Sep 2016 04:07:21 GMT
RUN set -x 	&& apt-get update 	&& apt-get install -y --no-install-recommends logstash=$LOGSTASH_VERSION 	&& rm -rf /var/lib/apt/lists/*
# Sat, 24 Sep 2016 04:07:22 GMT
ENV PATH=/opt/logstash/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Sat, 24 Sep 2016 04:07:22 GMT
ENV LS_SETTINGS_DIR=/etc/logstash
# Sat, 24 Sep 2016 04:07:23 GMT
RUN set -ex 	&& if [ -f "$LS_SETTINGS_DIR/logstash.yml" ]; then 		sed -ri 's!^(path.log|path.config):!#&!g' "$LS_SETTINGS_DIR/logstash.yml"; 	fi
# Sat, 24 Sep 2016 04:07:23 GMT
COPY file:e25e9bbce7bd2a5373b3d6a54afe70f3338f9e3fb5fc933284ea0d73eaa8985c in / 
# Sat, 24 Sep 2016 04:07:24 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Sat, 24 Sep 2016 04:07:24 GMT
CMD ["-e" ""]
```

-	Layers:
	-	`sha256:6a5a5368e0c2d3e5909184fa28ddfd56072e7ff3ee9a945876f7eee5896ef5bb`  
		Last Modified: Fri, 23 Sep 2016 18:10:19 GMT  
		Size: 51.4 MB (51354364 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7b9457ec39de00bc70af1c9631b9ae6ede5a3ab715e6492c0a2641868ec1deda`  
		Last Modified: Fri, 23 Sep 2016 18:25:33 GMT  
		Size: 18.5 MB (18528257 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d5cc639e6fca6aa608423c71badb1c40bacbd0b4a1bbe563b439d831a3c55298`  
		Last Modified: Fri, 23 Sep 2016 19:33:38 GMT  
		Size: 566.5 KB (566547 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2cac98b7f5b9c75d78082095f3348899dc83c3d6f1968dc68877c9d32798f65d`  
		Last Modified: Fri, 23 Sep 2016 19:38:15 GMT  
		Size: 219.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bf96dd67c9aae18b5b25c15de2a12d9cb64d6fb227e3f25fdb4e453da4293c64`  
		Last Modified: Fri, 23 Sep 2016 19:38:14 GMT  
		Size: 242.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ab05ba8362e2ac429a4c24286f80d2f623a6ba32184abfe76174e635304d7afa`  
		Last Modified: Fri, 23 Sep 2016 19:38:25 GMT  
		Size: 53.4 MB (53401902 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fa7e8f9f253c0a41ebf41be1054ebb4c2b7e6d465bb59135f16a01614a7c8370`  
		Last Modified: Fri, 23 Sep 2016 19:38:14 GMT  
		Size: 284.2 KB (284172 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a9bfca5875d5a918f885dd63e601a05072ed5f9c2e8e13021362debe1685a05d`  
		Last Modified: Sat, 24 Sep 2016 04:06:13 GMT  
		Size: 933.7 KB (933669 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:715d53b08fd39fece791013a4af74a712bd4932cb01eff198b5aa6698193d92d`  
		Last Modified: Sat, 24 Sep 2016 04:06:12 GMT  
		Size: 194.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0f7382a6e35f745215b7c945b250d616fbfd6cdbfc3d6c9495b490fb47ce428a`  
		Last Modified: Sat, 24 Sep 2016 04:06:09 GMT  
		Size: 807.9 KB (807933 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:eb5ccf9bfa127f45e158f1c41595547bd95d84b2cd04b35668f3e8c02c922b5e`  
		Last Modified: Sat, 24 Sep 2016 04:06:09 GMT  
		Size: 1.5 KB (1454 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ebf5c28ce08b28bc06a6147658bb80471f44911f8b0220cf7b71f64bd5346e69`  
		Last Modified: Sat, 24 Sep 2016 04:07:32 GMT  
		Size: 223.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:28e4793419726d9250a44aadef16c6b23fc7ac1e1a924361a837e678d97be28b`  
		Last Modified: Sat, 24 Sep 2016 04:07:45 GMT  
		Size: 84.8 MB (84803872 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:dbb3a7e4cf217f70cfc96a3af18a27851d83ec9a2431a7942c6a206580c6ebc9`  
		Last Modified: Sat, 24 Sep 2016 04:07:32 GMT  
		Size: 251.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
