## `httpd:latest`

```console
$ docker pull httpd@sha256:aa0711c4fc25264ce59b5f9315b555ba1252ad0fbd0e290634b693df2045a072
```

-	Platforms:
	-	linux; amd64

### `httpd:latest` - linux; amd64

-	Docker Version: 1.12.1
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **71.9 MB (71936145 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:9ca4bda0a6b3727a6ffcc43e981cad0f24e2ec79d338f6ba325b4dfd0756fb8f`
-	Default Command: `["httpd-foreground"]`

```dockerfile
# Fri, 23 Sep 2016 18:08:50 GMT
ADD file:c6c23585ab140b0b320d4e99bc1b0eb544c9e96c24d90fec5e069a6d57d335ca in / 
# Fri, 23 Sep 2016 18:08:51 GMT
CMD ["/bin/bash"]
# Fri, 23 Sep 2016 19:16:40 GMT
ENV HTTPD_PREFIX=/usr/local/apache2
# Fri, 23 Sep 2016 19:16:41 GMT
ENV PATH=/usr/local/apache2/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 23 Sep 2016 19:16:41 GMT
RUN mkdir -p "$HTTPD_PREFIX" 	&& chown www-data:www-data "$HTTPD_PREFIX"
# Fri, 23 Sep 2016 19:16:42 GMT
WORKDIR /usr/local/apache2
# Fri, 23 Sep 2016 19:16:54 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		libapr1 		libaprutil1 		libaprutil1-ldap 		libapr1-dev 		libaprutil1-dev 		libpcre++0 		libssl1.0.0 	&& rm -r /var/lib/apt/lists/*
# Fri, 23 Sep 2016 19:16:55 GMT
ENV HTTPD_VERSION=2.4.23
# Fri, 23 Sep 2016 19:16:55 GMT
ENV HTTPD_SHA1=5101be34ac4a509b245adb70a56690a84fcc4e7f
# Fri, 23 Sep 2016 23:19:03 GMT
ENV HTTPD_BZ2_URL=https://www.apache.org/dyn/closer.cgi?action=download&filename=httpd/httpd-2.4.23.tar.bz2
# Fri, 23 Sep 2016 23:19:04 GMT
ENV HTTPD_ASC_URL=https://www.apache.org/dist/httpd/httpd-2.4.23.tar.bz2.asc
# Fri, 23 Sep 2016 23:20:44 GMT
RUN set -x 	&& buildDeps=' 		bzip2 		ca-certificates 		gcc 		libpcre++-dev 		libssl-dev 		make 		wget 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -r /var/lib/apt/lists/* 		&& wget -O httpd.tar.bz2 "$HTTPD_BZ2_URL" 	&& echo "$HTTPD_SHA1 *httpd.tar.bz2" | sha1sum -c - 	&& wget -O httpd.tar.bz2.asc "$HTTPD_ASC_URL" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys A93D62ECC3C8EA12DB220EC934EA76E6791485A8 	&& gpg --batch --verify httpd.tar.bz2.asc httpd.tar.bz2 	&& rm -r "$GNUPGHOME" httpd.tar.bz2.asc 		&& mkdir -p src 	&& tar -xvf httpd.tar.bz2 -C src --strip-components=1 	&& rm httpd.tar.bz2 	&& cd src 		&& ./configure 		--prefix="$HTTPD_PREFIX" 		--enable-mods-shared=reallyall 	&& make -j"$(nproc)" 	&& make install 		&& cd .. 	&& rm -r src 		&& sed -ri 		-e 's!^(\s*CustomLog)\s+\S+!\1 /proc/self/fd/1!g' 		-e 's!^(\s*ErrorLog)\s+\S+!\1 /proc/self/fd/2!g' 		"$HTTPD_PREFIX/conf/httpd.conf" 		&& apt-get purge -y --auto-remove $buildDeps
# Fri, 23 Sep 2016 23:20:45 GMT
COPY file:761e313354b918b6cd7ea99975a4f6b53ff5381ba689bab2984aec4dab597215 in /usr/local/bin/ 
# Fri, 23 Sep 2016 23:20:45 GMT
EXPOSE 80/tcp
# Fri, 23 Sep 2016 23:20:45 GMT
CMD ["httpd-foreground"]
```

-	Layers:
	-	`sha256:6a5a5368e0c2d3e5909184fa28ddfd56072e7ff3ee9a945876f7eee5896ef5bb`  
		Last Modified: Fri, 23 Sep 2016 18:10:19 GMT  
		Size: 51.4 MB (51354364 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1bbf5d58d24c47512e234a5623474acf65ae00d4d1414272a893204f44cc680c`  
		Last Modified: Fri, 23 Sep 2016 19:18:07 GMT  
		Size: 150.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8f5dc8a4b12c307ac84de90cdd9a7f3915d1be04c9388868ca118831099c67a9`  
		Last Modified: Fri, 23 Sep 2016 19:18:10 GMT  
		Size: 11.7 MB (11739507 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bbd6b22eb11afce63cc76f6bc41042d99f10d6024c96b655dafba930b8d25909`  
		Last Modified: Fri, 23 Sep 2016 23:23:14 GMT  
		Size: 8.8 MB (8841833 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:960e52ecf8200cbd84e70eb2ad8678f4367e50d14357021872c10fa3fc5935fa`  
		Last Modified: Fri, 23 Sep 2016 23:23:11 GMT  
		Size: 291.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
