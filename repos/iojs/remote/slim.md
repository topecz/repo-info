## `iojs:slim`

```console
$ docker pull iojs@sha256:be8b1e46c2cae33a2817c2f9460e3cccea7d109aa7ccb9f86f5a2aa527f64f7a
```

-	Platforms:
	-	linux; amd64

### `iojs:slim` - linux; amd64

-	Docker Version: 1.12.1
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **81.4 MB (81399374 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:1d72480866fa3011c0594c5cbbbca3394b02a74eb6a84b011232d225f73d749d`
-	Default Command: `["iojs"]`

```dockerfile
# Fri, 23 Sep 2016 18:08:50 GMT
ADD file:c6c23585ab140b0b320d4e99bc1b0eb544c9e96c24d90fec5e069a6d57d335ca in / 
# Fri, 23 Sep 2016 18:08:51 GMT
CMD ["/bin/bash"]
# Fri, 23 Sep 2016 18:25:17 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Fri, 23 Sep 2016 19:21:28 GMT
RUN set -ex   && for key in     9554F04D7259F04124DE6B476D5A82AC7E37093B     94AE36675C464D64BAFA68DD7434390BDBE9B9C5     0034A06D9D9B0064CE8ADF6BF1747F4AD2306D93     FD3A5288F042B6850C66B31F09FE44734EB7990E     71DCFD284A79C3B38668286BC97EC7A07EDE3FC1     DD8F2338BAE7501E3DD5AC78C273792F7D83545D   ; do     gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"   ; done
# Fri, 23 Sep 2016 19:21:28 GMT
ENV NPM_CONFIG_LOGLEVEL=info
# Fri, 23 Sep 2016 19:24:08 GMT
ENV IOJS_VERSION=3.3.0
# Fri, 23 Sep 2016 19:24:29 GMT
RUN curl -SLO "https://iojs.org/dist/v$IOJS_VERSION/iojs-v$IOJS_VERSION-linux-x64.tar.gz"   && curl -SLO "https://iojs.org/dist/v$IOJS_VERSION/SHASUMS256.txt.asc"   && gpg --verify SHASUMS256.txt.asc   && grep " iojs-v$IOJS_VERSION-linux-x64.tar.gz\$" SHASUMS256.txt.asc | sha256sum -c -   && tar -xzf "iojs-v$IOJS_VERSION-linux-x64.tar.gz" -C /usr/local --strip-components=1   && rm "iojs-v$IOJS_VERSION-linux-x64.tar.gz" SHASUMS256.txt.asc
# Fri, 23 Sep 2016 19:24:30 GMT
CMD ["iojs"]
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
	-	`sha256:bd84a347fd2158d474b87a2d78a8aa9e4538772fe89f84ae47bc146a9527bf8c`  
		Last Modified: Fri, 23 Sep 2016 19:21:40 GMT  
		Size: 34.4 KB (34437 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c9619f848463afdd95e85de5b510f1ce34f683e3a0de7f9d87416e97d13991ef`  
		Last Modified: Fri, 23 Sep 2016 19:24:41 GMT  
		Size: 11.5 MB (11482316 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
