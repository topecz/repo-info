## `jenkins:alpine`

```console
$ docker pull jenkins@sha256:a07be7209970b27aed7aa7596c937b04f1416edc4d8a0e134eb5e4c92bbff472
```

-	Platforms:
	-	linux; amd64

### `jenkins:alpine` - linux; amd64

-	Docker Version: 1.12.1
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **144.1 MB (144097424 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:7281ecb27b979500082bef4985abaf7dfc743d213a9bc21cfbb2fd2aca1977f2`
-	Entrypoint: `["\/bin\/tini","--","\/usr\/local\/bin\/jenkins.sh"]`

```dockerfile
# Fri, 23 Sep 2016 16:29:57 GMT
ADD file:d6ee3ba7a4d59b161917082cc7242c660c61bb3f3cc1549c7e2dfff2b0de7104 in / 
# Fri, 23 Sep 2016 17:02:28 GMT
ENV LANG=C.UTF-8
# Fri, 23 Sep 2016 17:02:29 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Fri, 23 Sep 2016 17:05:12 GMT
ENV JAVA_HOME=/usr/lib/jvm/java-1.8-openjdk
# Fri, 23 Sep 2016 17:05:13 GMT
ENV PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/lib/jvm/java-1.8-openjdk/jre/bin:/usr/lib/jvm/java-1.8-openjdk/bin
# Fri, 23 Sep 2016 17:05:13 GMT
ENV JAVA_VERSION=8u92
# Fri, 23 Sep 2016 17:05:13 GMT
ENV JAVA_ALPINE_VERSION=8.92.14-r1
# Fri, 23 Sep 2016 17:05:18 GMT
RUN set -x 	&& apk add --no-cache 		openjdk8="$JAVA_ALPINE_VERSION" 	&& [ "$JAVA_HOME" = "$(docker-java-home)" ]
# Fri, 23 Sep 2016 18:51:27 GMT
RUN apk add --no-cache git openssh-client curl zip unzip bash ttf-dejavu coreutils
# Fri, 23 Sep 2016 18:51:27 GMT
ENV JENKINS_HOME=/var/jenkins_home
# Fri, 23 Sep 2016 18:51:27 GMT
ENV JENKINS_SLAVE_AGENT_PORT=50000
# Fri, 23 Sep 2016 18:51:28 GMT
ARG user=jenkins
# Fri, 23 Sep 2016 18:51:28 GMT
ARG group=jenkins
# Fri, 23 Sep 2016 18:51:29 GMT
ARG uid=1000
# Fri, 23 Sep 2016 18:51:29 GMT
ARG gid=1000
# Fri, 23 Sep 2016 18:51:31 GMT
# ARGS: gid=1000 group=jenkins uid=1000 user=jenkins
RUN addgroup -g ${gid} ${group}     && adduser -h "$JENKINS_HOME" -u ${uid} -G ${group} -s /bin/bash -D ${user}
# Fri, 23 Sep 2016 18:51:31 GMT
VOLUME [/var/jenkins_home]
# Fri, 23 Sep 2016 18:51:32 GMT
# ARGS: gid=1000 group=jenkins uid=1000 user=jenkins
RUN mkdir -p /usr/share/jenkins/ref/init.groovy.d
# Fri, 23 Sep 2016 18:51:33 GMT
ENV TINI_VERSION=0.9.0
# Fri, 23 Sep 2016 18:51:33 GMT
ENV TINI_SHA=fa23d1e20732501c3bb8eeeca423c89ac80ed452
# Fri, 23 Sep 2016 18:51:36 GMT
# ARGS: gid=1000 group=jenkins uid=1000 user=jenkins
RUN curl -fsSL https://github.com/krallin/tini/releases/download/v${TINI_VERSION}/tini-static -o /bin/tini && chmod +x /bin/tini   && echo "$TINI_SHA  /bin/tini" | sha1sum -c -
# Fri, 23 Sep 2016 18:51:37 GMT
COPY file:c629bc0b9ecb5b7233000c973f65721df4ce1307a5d5b33ac3871ff61a9172ff in /usr/share/jenkins/ref/init.groovy.d/tcp-slave-agent-port.groovy 
# Fri, 23 Sep 2016 18:51:37 GMT
ARG JENKINS_VERSION
# Fri, 23 Sep 2016 18:51:37 GMT
ENV JENKINS_VERSION=2.7.4
# Fri, 23 Sep 2016 18:51:38 GMT
ARG JENKINS_SHA=07a2e3e4ace728fdbcc823f46068d2f8cc3cb97b
# Fri, 23 Sep 2016 18:51:38 GMT
ARG JENKINS_URL=http://repo.jenkins-ci.org/public/org/jenkins-ci/main/jenkins-war/2.7.4/jenkins-war-2.7.4.war
# Fri, 23 Sep 2016 18:51:44 GMT
# ARGS: JENKINS_SHA=07a2e3e4ace728fdbcc823f46068d2f8cc3cb97b JENKINS_URL=http://repo.jenkins-ci.org/public/org/jenkins-ci/main/jenkins-war/2.7.4/jenkins-war-2.7.4.war gid=1000 group=jenkins uid=1000 user=jenkins
RUN curl -fsSL ${JENKINS_URL} -o /usr/share/jenkins/jenkins.war   && echo "${JENKINS_SHA}  /usr/share/jenkins/jenkins.war" | sha1sum -c -
# Fri, 23 Sep 2016 18:51:44 GMT
ENV JENKINS_UC=https://updates.jenkins.io
# Fri, 23 Sep 2016 18:51:46 GMT
# ARGS: JENKINS_SHA=07a2e3e4ace728fdbcc823f46068d2f8cc3cb97b JENKINS_URL=http://repo.jenkins-ci.org/public/org/jenkins-ci/main/jenkins-war/2.7.4/jenkins-war-2.7.4.war gid=1000 group=jenkins uid=1000 user=jenkins
RUN chown -R ${user} "$JENKINS_HOME" /usr/share/jenkins/ref
# Fri, 23 Sep 2016 18:51:46 GMT
EXPOSE 8080/tcp
# Fri, 23 Sep 2016 18:51:46 GMT
EXPOSE 50000/tcp
# Fri, 23 Sep 2016 18:51:47 GMT
ENV COPY_REFERENCE_FILE_LOG=/var/jenkins_home/copy_reference_file.log
# Fri, 23 Sep 2016 18:51:47 GMT
USER [jenkins]
# Fri, 23 Sep 2016 18:51:48 GMT
COPY file:26c3c5818bc87662d1f4905a3ed73bd55a0a75f731c7dc52d0599c00f51408e9 in /usr/local/bin/jenkins-support 
# Fri, 23 Sep 2016 18:51:49 GMT
COPY file:fc94121cf01d6d05be390499fbde73a26d1cf59af88d4d29dab5e81024778028 in /usr/local/bin/jenkins.sh 
# Fri, 23 Sep 2016 18:51:49 GMT
ENTRYPOINT ["/bin/tini" "--" "/usr/local/bin/jenkins.sh"]
# Fri, 23 Sep 2016 18:51:50 GMT
COPY file:902c50db7f531a8fe363c937a24f6474b4525ed70c2b3d807306d33d6d254a9d in /usr/local/bin/plugins.sh 
# Fri, 23 Sep 2016 18:51:50 GMT
COPY file:c9cb5b680a6dd3e26901cca8c795d5aacfe8ff25d6bfc2e19624e203933efea7 in /usr/local/bin/install-plugins.sh 
```

-	Layers:
	-	`sha256:c0cb142e43453ebb1f82b905aa472e6e66017efd43872135bc5372e4fac04031`  
		Last Modified: Fri, 23 Sep 2016 16:30:54 GMT  
		Size: 2.3 MB (2312930 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bf00e3870fb3e40e4a8e049bc0cd0d95ccd634da7b4b9980004b819f064fa174`  
		Last Modified: Fri, 23 Sep 2016 17:02:49 GMT  
		Size: 231.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9536b9909f79d52b70efe60abe868e66019b131e7618f3498475b236a756e2ad`  
		Last Modified: Fri, 23 Sep 2016 17:05:37 GMT  
		Size: 49.3 MB (49325354 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8cb05a826f85514b9cc1374bd6d6283fcd3f0187b22c47f9d43453336676513e`  
		Last Modified: Fri, 23 Sep 2016 18:52:14 GMT  
		Size: 23.5 MB (23461346 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a942b86455c71e14cdd87a700dfb5972676cd9924ca45959448349df2e747339`  
		Last Modified: Fri, 23 Sep 2016 18:52:05 GMT  
		Size: 1.3 KB (1266 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:698895b5a486a22b3a5d7685c3b1e93114fea0162d217ff5949ee4499a4f2b13`  
		Last Modified: Fri, 23 Sep 2016 18:52:03 GMT  
		Size: 175.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f608d71c0b8c45cfcb748bcb0769293bf1732ca9ca3fd2fcbef92735954d04b9`  
		Last Modified: Fri, 23 Sep 2016 18:52:03 GMT  
		Size: 337.2 KB (337238 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:dbb78415c6d6cf72f01f60cf3934136aa3912ef1f969dd0cee3a0b9bcf1eb978`  
		Last Modified: Fri, 23 Sep 2016 18:52:02 GMT  
		Size: 421.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c8b2fe170902b79bb27151e6ef273b9c81f507abbf13ae394fbc2707b4041585`  
		Last Modified: Fri, 23 Sep 2016 18:52:09 GMT  
		Size: 68.7 MB (68652375 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:05ef9ba9b6dda9b22a08f2a72bf479363b23176a986a3a3be59538d3a63d4587`  
		Last Modified: Fri, 23 Sep 2016 18:52:00 GMT  
		Size: 427.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:36cbe135af38ac90eba24bbac6128d14cfab1ca7aecc05f9f68bbac401fbfd34`  
		Last Modified: Fri, 23 Sep 2016 18:52:00 GMT  
		Size: 1.4 KB (1413 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d42f84363f9a4929bcb8a2dde1f5ce48dc4494b78fd4d704431ec37aff394580`  
		Last Modified: Fri, 23 Sep 2016 18:51:59 GMT  
		Size: 632.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7aae2d88978b46947fe177dbe84549ea8d263a25863826fe9595b8b455246d37`  
		Last Modified: Fri, 23 Sep 2016 18:52:02 GMT  
		Size: 1.5 KB (1491 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7d9a7929a790f96332355ec89ddca259b17fee3c92ea8414df5a80524f78cb5f`  
		Last Modified: Fri, 23 Sep 2016 18:51:59 GMT  
		Size: 2.1 KB (2125 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
