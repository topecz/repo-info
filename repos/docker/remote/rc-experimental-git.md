## `docker:rc-experimental-git`

```console
$ docker pull docker@sha256:57fb8532b97c278068893d316c53c898de692f533b9013404e40c4e0aab564d0
```

-	Platforms:
	-	linux; amd64

### `docker:rc-experimental-git` - linux; amd64

-	Docker Version: 1.12.1
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **41.3 MB (41252217 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:d656bd186b469b2218e35fa0fcad946ce619461e898a5cd8c956c57241212637`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["sh"]`

```dockerfile
# Fri, 23 Sep 2016 16:29:57 GMT
ADD file:d6ee3ba7a4d59b161917082cc7242c660c61bb3f3cc1549c7e2dfff2b0de7104 in / 
# Fri, 23 Sep 2016 16:36:54 GMT
RUN apk add --no-cache 		ca-certificates 		curl 		openssl
# Fri, 23 Sep 2016 16:38:38 GMT
ENV DOCKER_BUCKET=experimental.docker.com
# Wed, 28 Sep 2016 20:49:23 GMT
ENV DOCKER_VERSION=1.12.2-rc1
# Wed, 28 Sep 2016 20:49:23 GMT
ENV DOCKER_SHA256=d3096cd00f8386e5180c24c7d93284a725577194b43404960029f861fd5a71db
# Wed, 28 Sep 2016 20:49:30 GMT
RUN set -x 	&& curl -fSL "https://${DOCKER_BUCKET}/builds/Linux/x86_64/docker-${DOCKER_VERSION}.tgz" -o docker.tgz 	&& echo "${DOCKER_SHA256} *docker.tgz" | sha256sum -c - 	&& tar -xzvf docker.tgz 	&& mv docker/* /usr/local/bin/ 	&& rmdir docker 	&& rm docker.tgz 	&& docker -v
# Wed, 28 Sep 2016 20:49:35 GMT
COPY file:50006c902e7677711aeffe4ab7b7042d649618b96dec760f322a8566dd83ab25 in /usr/local/bin/ 
# Wed, 28 Sep 2016 20:49:35 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Wed, 28 Sep 2016 20:49:35 GMT
CMD ["sh"]
# Wed, 28 Sep 2016 20:49:48 GMT
RUN apk add --no-cache 		git 		openssh-client
```

-	Layers:
	-	`sha256:c0cb142e43453ebb1f82b905aa472e6e66017efd43872135bc5372e4fac04031`  
		Last Modified: Fri, 23 Sep 2016 16:30:54 GMT  
		Size: 2.3 MB (2312930 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6c6fe447e877c6fb78f7040d59f81a9aaac5be90ed3f7396a6dfd9aaa3467d29`  
		Last Modified: Fri, 23 Sep 2016 16:37:07 GMT  
		Size: 915.0 KB (915035 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:14d929ed1b815c6bbdc077a735ac7d2cdf1c6f0e90827013fd64d5f6a3365eec`  
		Last Modified: Wed, 28 Sep 2016 20:52:27 GMT  
		Size: 28.9 MB (28885230 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8f643d591089ee9d0ff7234cafa746f94c205ec40a63e5eef7711ce9fec362cc`  
		Last Modified: Wed, 28 Sep 2016 20:52:14 GMT  
		Size: 466.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:865ab309a165b28b093c2183c17200443a6590536af583405b0f11fef35e457a`  
		Last Modified: Wed, 28 Sep 2016 20:53:56 GMT  
		Size: 9.1 MB (9138556 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
