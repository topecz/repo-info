## `docker:rc`

```console
$ docker pull docker@sha256:0a6652336b26d0abdfc50cc51f32c3eb4a557ecb8b9e6a1e11b457ce7ae6e6cf
```

-	Platforms:
	-	linux; amd64

### `docker:rc` - linux; amd64

-	Docker Version: 1.12.1
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **32.0 MB (31974445 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:1a71ed9a552352fa87f610a8c0a144cc2753de81a82adfd5af302c9589c8ceca`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["sh"]`

```dockerfile
# Fri, 23 Sep 2016 16:29:57 GMT
ADD file:d6ee3ba7a4d59b161917082cc7242c660c61bb3f3cc1549c7e2dfff2b0de7104 in / 
# Fri, 23 Sep 2016 16:36:54 GMT
RUN apk add --no-cache 		ca-certificates 		curl 		openssl
# Wed, 28 Sep 2016 20:49:07 GMT
ENV DOCKER_BUCKET=test.docker.com
# Wed, 28 Sep 2016 20:49:07 GMT
ENV DOCKER_VERSION=1.12.2-rc1
# Wed, 28 Sep 2016 20:49:08 GMT
ENV DOCKER_SHA256=0629b1681343ce333c5125670d63c2ca4e090f9d7de39f822ad35445eef124db
# Wed, 28 Sep 2016 20:49:12 GMT
RUN set -x 	&& curl -fSL "https://${DOCKER_BUCKET}/builds/Linux/x86_64/docker-${DOCKER_VERSION}.tgz" -o docker.tgz 	&& echo "${DOCKER_SHA256} *docker.tgz" | sha256sum -c - 	&& tar -xzvf docker.tgz 	&& mv docker/* /usr/local/bin/ 	&& rmdir docker 	&& rm docker.tgz 	&& docker -v
# Wed, 28 Sep 2016 20:49:12 GMT
COPY file:50006c902e7677711aeffe4ab7b7042d649618b96dec760f322a8566dd83ab25 in /usr/local/bin/ 
# Wed, 28 Sep 2016 20:49:13 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Wed, 28 Sep 2016 20:49:13 GMT
CMD ["sh"]
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
	-	`sha256:34126b998a61be249482095d9bbb59689035cd9dd9c452073f7e3f3f46699617`  
		Last Modified: Wed, 28 Sep 2016 20:50:14 GMT  
		Size: 28.7 MB (28746014 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7da62528f60c2095c511a9ce542486382465c1905e263e1ef3c011646a4a5f5e`  
		Last Modified: Wed, 28 Sep 2016 20:50:02 GMT  
		Size: 466.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
