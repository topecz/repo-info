## `tomcat:latest`

```console
$ docker pull tomcat@sha256:87025ccebdd5534826b4d315ceda1a97ba75e35431075eeaacaf616998a46ed0
```

-	Platforms:
	-	linux; amd64

### `tomcat:latest` - linux; amd64

-	Docker Version: 1.12.1
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **161.3 MB (161342141 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:30d95ba23356c135ca73b2e6a83fb7c5f8a35a7a6b5a2d57ced9adedc47badb4`
-	Default Command: `["catalina.sh","run"]`

```dockerfile
# Fri, 23 Sep 2016 18:08:50 GMT
ADD file:c6c23585ab140b0b320d4e99bc1b0eb544c9e96c24d90fec5e069a6d57d335ca in / 
# Fri, 23 Sep 2016 18:08:51 GMT
CMD ["/bin/bash"]
# Fri, 23 Sep 2016 18:25:17 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Fri, 23 Sep 2016 19:32:51 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Fri, 23 Sep 2016 19:32:51 GMT
ENV LANG=C.UTF-8
# Fri, 23 Sep 2016 19:32:52 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Fri, 23 Sep 2016 19:32:52 GMT
ENV JAVA_HOME=/usr/lib/jvm/java-7-openjdk-amd64/jre
# Fri, 23 Sep 2016 19:32:53 GMT
ENV JAVA_VERSION=7u111
# Fri, 23 Sep 2016 19:32:53 GMT
ENV JAVA_DEBIAN_VERSION=7u111-2.6.7-1~deb8u1
# Fri, 23 Sep 2016 19:33:30 GMT
RUN set -x 	&& apt-get update 	&& apt-get install -y 		openjdk-7-jre-headless="$JAVA_DEBIAN_VERSION" 	&& rm -rf /var/lib/apt/lists/* 	&& [ "$JAVA_HOME" = "$(docker-java-home)" ]
# Fri, 23 Sep 2016 23:44:27 GMT
ENV CATALINA_HOME=/usr/local/tomcat
# Fri, 23 Sep 2016 23:44:28 GMT
ENV PATH=/usr/local/tomcat/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 23 Sep 2016 23:44:29 GMT
RUN mkdir -p "$CATALINA_HOME"
# Fri, 23 Sep 2016 23:44:29 GMT
WORKDIR /usr/local/tomcat
# Fri, 23 Sep 2016 23:48:31 GMT
ENV TOMCAT_NATIVE_LIBDIR=/usr/local/tomcat/native-jni-lib
# Fri, 23 Sep 2016 23:48:32 GMT
ENV LD_LIBRARY_PATH=/usr/local/tomcat/native-jni-lib
# Fri, 23 Sep 2016 23:48:32 GMT
ENV OPENSSL_VERSION=1.0.2i-1
# Fri, 23 Sep 2016 23:48:33 GMT
RUN { 		echo 'deb http://httpredir.debian.org/debian unstable main'; 	} > /etc/apt/sources.list.d/unstable.list 	&& { 		echo 'Package: *'; 		echo 'Pin: release a=unstable'; 		echo 'Pin-Priority: -10'; 		echo; 		echo 'Package: openssl libssl*'; 		echo "Pin: version $OPENSSL_VERSION"; 		echo 'Pin-Priority: 990'; 	} > /etc/apt/preferences.d/unstable-openssl
# Fri, 23 Sep 2016 23:48:42 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		libapr1 		openssl="$OPENSSL_VERSION" 	&& rm -rf /var/lib/apt/lists/*
# Fri, 23 Sep 2016 23:48:50 GMT
RUN set -ex 	&& for key in 		05AB33110949707C93A279E3D3EFE6B686867BA6 		07E48665A34DCAFAE522E5E6266191C37C037D42 		47309207D818FFD8DCD3F83F1931D684307A10A5 		541FBE7D8F78B25E055DDEE13C370389288584E7 		61B832AC2F1C5A90F0F9B00A1C506407564C17A3 		713DA88BE50911535FE716F5208B0AB1D63011C7 		79F7026C690BAA50B92CD8B66A3AD3F4F22C4FED 		9BA44C2621385CB966EBA586F72C284D731FABEE 		A27677289986DB50844682F8ACB77FC2E86E29AC 		A9C5DF4D22E99998D9875A5110C01C5A2F6059E7 		DCFD35E0BF8CA7344752DE8B6FB21E8933C60243 		F3A04C595DB5B6A5F1ECA43E3B7BBB100D811BBE 		F7DA48BB64BCB84ECBA7EE6935CD23C10D498E23 	; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	done
# Fri, 23 Sep 2016 23:52:37 GMT
ENV TOMCAT_MAJOR=8
# Fri, 23 Sep 2016 23:52:38 GMT
ENV TOMCAT_VERSION=8.0.37
# Fri, 23 Sep 2016 23:52:38 GMT
ENV TOMCAT_TGZ_URL=https://www.apache.org/dyn/closer.cgi?action=download&filename=tomcat/tomcat-8/v8.0.37/bin/apache-tomcat-8.0.37.tar.gz
# Fri, 23 Sep 2016 23:52:38 GMT
ENV TOMCAT_ASC_URL=https://www.apache.org/dist/tomcat/tomcat-8/v8.0.37/bin/apache-tomcat-8.0.37.tar.gz.asc
# Fri, 23 Sep 2016 23:53:19 GMT
RUN set -x 		&& wget -O tomcat.tar.gz "$TOMCAT_TGZ_URL" 	&& wget -O tomcat.tar.gz.asc "$TOMCAT_ASC_URL" 	&& gpg --batch --verify tomcat.tar.gz.asc tomcat.tar.gz 	&& tar -xvf tomcat.tar.gz --strip-components=1 	&& rm bin/*.bat 	&& rm tomcat.tar.gz* 		&& nativeBuildDir="$(mktemp -d)" 	&& tar -xvf bin/tomcat-native.tar.gz -C "$nativeBuildDir" --strip-components=1 	&& nativeBuildDeps=" 		gcc 		libapr1-dev 		libssl-dev 		make 		openjdk-${JAVA_VERSION%%[-~bu]*}-jdk=$JAVA_DEBIAN_VERSION 	" 	&& apt-get update && apt-get install -y --no-install-recommends $nativeBuildDeps && rm -rf /var/lib/apt/lists/* 	&& ( 		export CATALINA_HOME="$PWD" 		&& cd "$nativeBuildDir/native" 		&& ./configure 			--libdir="$TOMCAT_NATIVE_LIBDIR" 			--prefix="$CATALINA_HOME" 			--with-apr="$(which apr-1-config)" 			--with-java-home="$(docker-java-home)" 			--with-ssl=yes 		&& make -j$(nproc) 		&& make install 	) 	&& apt-get purge -y --auto-remove $nativeBuildDeps 	&& rm -rf "$nativeBuildDir" 	&& rm bin/tomcat-native.tar.gz
# Fri, 23 Sep 2016 23:53:20 GMT
RUN set -e 	&& nativeLines="$(catalina.sh configtest 2>&1)" 	&& nativeLines="$(echo "$nativeLines" | grep 'Apache Tomcat Native')" 	&& nativeLines="$(echo "$nativeLines" | sort -u)" 	&& if ! echo "$nativeLines" | grep 'INFO: Loaded APR based Apache Tomcat Native library' >&2; then 		echo >&2 "$nativeLines"; 		exit 1; 	fi
# Fri, 23 Sep 2016 23:53:21 GMT
EXPOSE 8080/tcp
# Fri, 23 Sep 2016 23:53:21 GMT
CMD ["catalina.sh" "run"]
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
	-	`sha256:dae3b0638638646d213f6edc2c16e52ddb60e20e07e4c2f091ff7e2928b10bd0`  
		Last Modified: Fri, 23 Sep 2016 19:33:37 GMT  
		Size: 240.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ab678d1c6f004857bf4dbca219e8111b0a5699350e84a2edeaaf7327612f66eb`  
		Last Modified: Fri, 23 Sep 2016 19:33:51 GMT  
		Size: 77.7 MB (77712461 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d5bf826c31530f2a9fe4d9e7d89e4f144bab16c07133729509fc7101b8f7fe4f`  
		Last Modified: Fri, 23 Sep 2016 23:45:40 GMT  
		Size: 144.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0081bad1df81d5e8d7818fc16d6b1c15f036fc609541b02493c367ff36d05a9b`  
		Last Modified: Fri, 23 Sep 2016 23:49:49 GMT  
		Size: 335.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8fafa3f26de44472a8a84c1719d5011f46b32b4322989d52108989bed0354bc5`  
		Last Modified: Fri, 23 Sep 2016 23:49:50 GMT  
		Size: 3.0 MB (3002234 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ae984359ed7e15d991eaf0e93e56af2217377c0201dafe83ae23c37f0e93109c`  
		Last Modified: Fri, 23 Sep 2016 23:49:49 GMT  
		Size: 107.8 KB (107783 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9175a2e1674f71ba2ea07c086bdabe7c8a86f68037094326b27a630def32d86b`  
		Last Modified: Fri, 23 Sep 2016 23:53:32 GMT  
		Size: 10.1 MB (10069644 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2e8f15e7442673d8f6b3f2a1a264e8638639f252b075698d326cc7ed27f11862`  
		Last Modified: Fri, 23 Sep 2016 23:53:29 GMT  
		Size: 132.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
