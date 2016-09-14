## `iojs:slim`

```console
$ docker pull iojs@sha256:3aecf5afcc5bba3bad7bca88932b28d2f834db472c803704a23b21db8db16468
```

-	Platforms:
	-	linux; amd64

### `iojs:slim` - linux; amd64

-	Docker Version: 1.10.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **81.4 MB (81404528 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:1b1967b96ce210cf7f62bbf8a362617ae680d54ee5383b744a154565af92ca79`
-	Default Command: `["iojs"]`

```dockerfile
# Thu, 28 Jul 2016 17:47:54 GMT
ADD file:0e0565652aa852f62033d99f84892216020d30f64521ded5e72d4940bc4c9697 in /
# Thu, 28 Jul 2016 17:47:55 GMT
CMD ["/bin/bash"]
# Thu, 28 Jul 2016 17:57:57 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Fri, 29 Jul 2016 04:35:00 GMT
RUN set -ex   && for key in     9554F04D7259F04124DE6B476D5A82AC7E37093B     94AE36675C464D64BAFA68DD7434390BDBE9B9C5     0034A06D9D9B0064CE8ADF6BF1747F4AD2306D93     FD3A5288F042B6850C66B31F09FE44734EB7990E     71DCFD284A79C3B38668286BC97EC7A07EDE3FC1     DD8F2338BAE7501E3DD5AC78C273792F7D83545D   ; do     gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"   ; done
# Fri, 29 Jul 2016 04:35:00 GMT
ENV NPM_CONFIG_LOGLEVEL=info
# Fri, 29 Jul 2016 04:35:01 GMT
ENV IOJS_VERSION=3.3.0
# Fri, 29 Jul 2016 04:35:10 GMT
RUN curl -SLO "https://iojs.org/dist/v$IOJS_VERSION/iojs-v$IOJS_VERSION-linux-x64.tar.gz"   && curl -SLO "https://iojs.org/dist/v$IOJS_VERSION/SHASUMS256.txt.asc"   && gpg --verify SHASUMS256.txt.asc   && grep " iojs-v$IOJS_VERSION-linux-x64.tar.gz\$" SHASUMS256.txt.asc | sha256sum -c -   && tar -xzf "iojs-v$IOJS_VERSION-linux-x64.tar.gz" -C /usr/local --strip-components=1   && rm "iojs-v$IOJS_VERSION-linux-x64.tar.gz" SHASUMS256.txt.asc
# Fri, 29 Jul 2016 04:35:11 GMT
CMD ["iojs"]
```

-	Layers:
	-	`sha256:357ea8c3d80bc25792e010facfc98aee5972ebc47e290eb0d5aea3671a901cab`  
		Last Modified: Thu, 28 Jul 2016 17:49:58 GMT  
		Size: 51.4 MB (51365611 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:52befadefd24601247558f63fcb2ccd96b79cbc447a148ea1d0aa2719a9ac3b1`  
		Last Modified: Thu, 28 Jul 2016 21:52:07 GMT  
		Size: 18.5 MB (18526978 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:07903f253134fec8bf9c4113894fac39b5c32e55f37df5701979dfeddfc9d76d`  
		Last Modified: Fri, 29 Jul 2016 04:35:20 GMT  
		Size: 29.6 KB (29620 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:14d1e991a35f00e79404c6a9db0391754b17d3a710677b1fb57a78869345e65c`  
		Last Modified: Fri, 29 Jul 2016 04:35:24 GMT  
		Size: 11.5 MB (11482319 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip