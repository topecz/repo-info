## `java:6b38-jdk`

```console
$ docker pull java@sha256:645319a05bda784fc9f91038fe35af87bd0cd79f5395c501f22f5c32118bcbeb
```

-	Platforms:
	-	linux; amd64

### `java:6b38-jdk` - linux; amd64

-	Docker Version: 1.12.1
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **187.0 MB (187045525 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:6e769ce0985acdd977b06bbdfffa67c60f8f4325a0d4196d635efbb5d0db5fb2`
-	Default Command: `["\/bin\/bash"]`

```dockerfile
# Mon, 19 Sep 2016 17:43:34 GMT
ADD file:b06eab13504d045bfba673dde1c6f5831a875e95146504a385baa101124f58f5 in / 
# Mon, 19 Sep 2016 17:43:35 GMT
CMD ["/bin/bash"]
# Mon, 19 Sep 2016 17:52:12 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Mon, 19 Sep 2016 17:52:33 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		mercurial 		openssh-client 		subversion 				procps 	&& rm -rf /var/lib/apt/lists/*
# Tue, 20 Sep 2016 04:49:39 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Tue, 20 Sep 2016 04:49:40 GMT
ENV LANG=C.UTF-8
# Tue, 20 Sep 2016 04:49:41 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 20 Sep 2016 04:49:41 GMT
ENV JAVA_HOME=/usr/lib/jvm/java-6-openjdk-amd64
# Tue, 20 Sep 2016 04:49:41 GMT
ENV JAVA_VERSION=6b38
# Tue, 20 Sep 2016 04:49:42 GMT
ENV JAVA_DEBIAN_VERSION=6b38-1.13.10-1~deb7u1
# Tue, 20 Sep 2016 04:50:35 GMT
RUN set -x 	&& apt-get update 	&& apt-get install -y 		openjdk-6-jdk="$JAVA_DEBIAN_VERSION" 	&& rm -rf /var/lib/apt/lists/* 	&& [ "$JAVA_HOME" = "$(docker-java-home)" ]
```

-	Layers:
	-	`sha256:0fbab137f56aaa195d66eae971694eb98df3e4ff6a91eb4fa9905994ef40e5a1`  
		Last Modified: Mon, 19 Sep 2016 17:48:55 GMT  
		Size: 37.2 MB (37214522 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:75c99d281faeeb2fa2099fbbcaa380e4a96a4e83bd7bb3583d410667debf7aaa`  
		Last Modified: Mon, 19 Sep 2016 18:03:18 GMT  
		Size: 6.7 MB (6731221 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c75c691829ac57648477d2256c2be0844f91886837a7738ff1d35ba143ddff16`  
		Last Modified: Mon, 19 Sep 2016 18:03:47 GMT  
		Size: 37.4 MB (37365131 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:50ea6856c91ac94e365dfe6a428749a58a7bfd27fc33fed439d49bffd979eb9b`  
		Last Modified: Wed, 21 Sep 2016 22:51:54 GMT  
		Size: 413.0 KB (413009 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d93d3888777ee45a8bc02db5c65ed521f68cc9f6aa58298f85240461a2e95f22`  
		Last Modified: Wed, 21 Sep 2016 22:51:53 GMT  
		Size: 239.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:30e3407357eb859531d3118f272c7e80d4edb2648da7452b4ceb76fbe5ea6bfb`  
		Last Modified: Wed, 21 Sep 2016 22:52:15 GMT  
		Size: 105.3 MB (105321403 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
