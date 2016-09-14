## `solr:5-alpine`

```console
$ docker pull solr@sha256:30f0768f0296bc7bf8772c14d7fc23ea73d67108a9770037993abf7a8ed3e530
```

-	Platforms:
	-	linux; amd64

### `solr:5-alpine` - linux; amd64

-	Docker Version: 1.12.1
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **179.2 MB (179167652 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:7f3c357c07a95015959c244b028c4ea6b21742a826a33a72246b8388801168bb`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["solr"]`

```dockerfile
# Mon, 29 Aug 2016 23:49:14 GMT
ADD file:852e9d0cb9d906535af512a89339fc70b2873a0f94defbcbe41cd44942dd6ac8 in / 
# Tue, 30 Aug 2016 19:53:16 GMT
ENV LANG=C.UTF-8
# Tue, 30 Aug 2016 19:53:17 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 30 Aug 2016 19:56:05 GMT
ENV JAVA_HOME=/usr/lib/jvm/java-1.8-openjdk/jre
# Tue, 30 Aug 2016 19:56:05 GMT
ENV PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/lib/jvm/java-1.8-openjdk/jre/bin:/usr/lib/jvm/java-1.8-openjdk/bin
# Tue, 30 Aug 2016 19:56:05 GMT
ENV JAVA_VERSION=8u92
# Tue, 30 Aug 2016 19:56:05 GMT
ENV JAVA_ALPINE_VERSION=8.92.14-r1
# Tue, 30 Aug 2016 19:56:10 GMT
RUN set -x 	&& apk add --no-cache 		openjdk8-jre="$JAVA_ALPINE_VERSION" 	&& [ "$JAVA_HOME" = "$(docker-java-home)" ]
# Tue, 30 Aug 2016 23:15:13 GMT
MAINTAINER Martijn Koster "mak-docker@greenhills.co.uk"
# Tue, 30 Aug 2016 23:15:13 GMT
ARG SOLR_DOWNLOAD_SERVER
# Tue, 30 Aug 2016 23:15:13 GMT
ARG GPG_KEYSERVER
# Tue, 30 Aug 2016 23:15:16 GMT
RUN apk add --no-cache         lsof         gnupg         tar         bash
# Tue, 30 Aug 2016 23:15:18 GMT
RUN apk add --no-cache ca-certificates wget &&         update-ca-certificates
# Tue, 30 Aug 2016 23:15:19 GMT
ENV SOLR_USER=solr
# Tue, 30 Aug 2016 23:15:19 GMT
ENV SOLR_UID=8983
# Tue, 30 Aug 2016 23:15:20 GMT
RUN addgroup -S -g $SOLR_UID $SOLR_USER &&   adduser -S -u $SOLR_UID -g $SOLR_USER $SOLR_USER
# Tue, 30 Aug 2016 23:15:20 GMT
ENV SOLR_KEY=EDF961FF03E647F9CA8A9C2C758051CCA3A13A7F
# Tue, 30 Aug 2016 23:15:27 GMT
RUN gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$SOLR_KEY"
# Tue, 30 Aug 2016 23:15:28 GMT
ENV GPG_KEYSERVER=hkp://ha.pool.sks-keyservers.net
# Tue, 30 Aug 2016 23:15:30 GMT
RUN gpg --keyserver "$GPG_KEYSERVER" --recv-keys "$SOLR_KEY"
# Fri, 09 Sep 2016 21:33:27 GMT
ENV SOLR_VERSION=5.5.3
# Fri, 09 Sep 2016 21:33:27 GMT
ENV SOLR_SHA256=74e8a924dac0e073854af121a6de9d58fe8cc315d16b57e17f429c6a91b0b065
# Fri, 09 Sep 2016 21:33:27 GMT
ENV SOLR_URL=https://archive.apache.org/dist/lucene/solr/5.5.3/solr-5.5.3.tgz
# Fri, 09 Sep 2016 21:33:43 GMT
RUN mkdir -p /opt/solr &&   echo "downloading $SOLR_URL" &&   wget -q $SOLR_URL -O /opt/solr.tgz &&   echo "downloading $SOLR_URL.asc" &&   wget -q $SOLR_URL.asc -O /opt/solr.tgz.asc &&   echo "$SOLR_SHA256 */opt/solr.tgz" | sha256sum -c - &&   (>&2 ls -l /opt/solr.tgz /opt/solr.tgz.asc) &&   gpg --batch --verify /opt/solr.tgz.asc /opt/solr.tgz &&   tar -C /opt/solr --extract --file /opt/solr.tgz --strip-components=1 &&   rm /opt/solr.tgz* &&   rm -Rf /opt/solr/docs/ &&   mkdir -p /opt/solr/server/solr/lib /opt/solr/server/solr/mycores &&   sed -i -e 's/#SOLR_PORT=8983/SOLR_PORT=8983/' /opt/solr/bin/solr.in.sh &&   sed -i -e '/-Dsolr.clustering.enabled=true/ a SOLR_OPTS="$SOLR_OPTS -Dsun.net.inetaddr.ttl=60 -Dsun.net.inetaddr.negative.ttl=60"' /opt/solr/bin/solr.in.sh &&   chown -R $SOLR_USER:$SOLR_USER /opt/solr &&   mkdir /docker-entrypoint-initdb.d /opt/docker-solr/
# Fri, 09 Sep 2016 21:33:44 GMT
COPY dir:e7e155eea31238308402c3128237b81a9d96ede91c8ac8361c75c62f06b63e9b in /opt/docker-solr/scripts 
# Fri, 09 Sep 2016 21:33:44 GMT
RUN chown -R $SOLR_USER:$SOLR_USER /opt/docker-solr
# Fri, 09 Sep 2016 21:33:45 GMT
ENV PATH=/opt/solr/bin:/opt/docker-solr/scripts:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/lib/jvm/java-1.8-openjdk/jre/bin:/usr/lib/jvm/java-1.8-openjdk/bin
# Fri, 09 Sep 2016 21:33:45 GMT
EXPOSE 8983/tcp
# Fri, 09 Sep 2016 21:33:45 GMT
WORKDIR /opt/solr
# Fri, 09 Sep 2016 21:33:45 GMT
USER [solr]
# Fri, 09 Sep 2016 21:33:46 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Fri, 09 Sep 2016 21:33:46 GMT
CMD ["solr"]
```

-	Layers:
	-	`sha256:e110a4a1794126ef308a49f2d65785af2f25538f06700721aad8283b81fdfa58`  
		Last Modified: Thu, 23 Jun 2016 19:56:16 GMT  
		Size: 2.3 MB (2310286 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a696cba1f6e865421664a7bf9bf585bcfaa924d56b7d2a112a799e00a7433791`  
		Last Modified: Tue, 30 Aug 2016 21:11:27 GMT  
		Size: 232.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bc427bd93e958b2f8b2cadc810c692edbba6856a8ff08434066b43be35ec6b68`  
		Last Modified: Tue, 30 Aug 2016 21:11:37 GMT  
		Size: 39.6 MB (39647584 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:14cfd928a2dc715f82d463ba785ab31419bbddef37c5b76a197be1155f7f59b0`  
		Last Modified: Tue, 30 Aug 2016 23:21:02 GMT  
		Size: 4.7 MB (4745499 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7713cddf263368bd31f25d897221a672943c507811ce2526c168d356423b0e0a`  
		Last Modified: Tue, 30 Aug 2016 23:20:59 GMT  
		Size: 606.8 KB (606820 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:273eb1ea78fd1291603b6f2133f3b68649887fd399b9b62efda462d702e5e340`  
		Last Modified: Tue, 30 Aug 2016 23:20:59 GMT  
		Size: 1.3 KB (1254 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8d7ef1841e1b359d6cdb32dc1e3dd748564a63e8d75928c081961322851a79ea`  
		Last Modified: Tue, 30 Aug 2016 23:20:56 GMT  
		Size: 7.6 KB (7644 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5fae23590a58aed0313b5728dde21b562d58979eeaa0a6d011d03820994030a9`  
		Last Modified: Tue, 30 Aug 2016 23:20:56 GMT  
		Size: 153.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7d4f6a6fdc7632aaa494b18c23aaf307d60642fd5c8539eb1f5911b413336a6a`  
		Last Modified: Fri, 09 Sep 2016 21:39:06 GMT  
		Size: 131.8 MB (131844426 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:89eef873c9d04c5831384053fb0258bfc4fdca83b369e3f853ddf35e4a80a4db`  
		Last Modified: Fri, 09 Sep 2016 21:38:54 GMT  
		Size: 1.9 KB (1875 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:76999d98074aadb44de357ccac082592369ad464bff9311cf5c92911fb1f1aa5`  
		Last Modified: Fri, 09 Sep 2016 21:38:54 GMT  
		Size: 1.9 KB (1879 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip