## `golang:1-onbuild`

```console
$ docker pull golang@sha256:22fb11e3266fcd4f1439c669863245e7ac8f79736e9f35656457e96ac0185184
```

-	Platforms:
	-	linux; amd64

### `golang:1-onbuild` - linux; amd64

-	Docker Version: 1.12.1
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **253.7 MB (253660477 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:087c714ab437d5d01ac0616b8e32e29511ea6f0c4f7b49bca65a32b96de4bbdb`
-	Default Command: `["go-wrapper","run"]`

```dockerfile
# Fri, 23 Sep 2016 18:08:50 GMT
ADD file:c6c23585ab140b0b320d4e99bc1b0eb544c9e96c24d90fec5e069a6d57d335ca in / 
# Fri, 23 Sep 2016 18:08:51 GMT
CMD ["/bin/bash"]
# Fri, 23 Sep 2016 18:25:17 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Fri, 23 Sep 2016 18:26:18 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		mercurial 		openssh-client 		subversion 				procps 	&& rm -rf /var/lib/apt/lists/*
# Wed, 28 Sep 2016 20:45:24 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		g++ 		gcc 		libc6-dev 		make 		pkg-config 	&& rm -rf /var/lib/apt/lists/*
# Wed, 28 Sep 2016 20:46:24 GMT
ENV GOLANG_VERSION=1.7.1
# Wed, 28 Sep 2016 20:46:25 GMT
ENV GOLANG_DOWNLOAD_URL=https://golang.org/dl/go1.7.1.linux-amd64.tar.gz
# Wed, 28 Sep 2016 20:46:25 GMT
ENV GOLANG_DOWNLOAD_SHA256=43ad621c9b014cde8db17393dc108378d37bc853aa351a6c74bf6432c1bbd182
# Wed, 28 Sep 2016 20:46:34 GMT
RUN curl -fsSL "$GOLANG_DOWNLOAD_URL" -o golang.tar.gz 	&& echo "$GOLANG_DOWNLOAD_SHA256  golang.tar.gz" | sha256sum -c - 	&& tar -C /usr/local -xzf golang.tar.gz 	&& rm golang.tar.gz
# Wed, 28 Sep 2016 20:46:35 GMT
ENV GOPATH=/go
# Wed, 28 Sep 2016 20:46:35 GMT
ENV PATH=/go/bin:/usr/local/go/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Wed, 28 Sep 2016 20:46:36 GMT
RUN mkdir -p "$GOPATH/src" "$GOPATH/bin" && chmod -R 777 "$GOPATH"
# Wed, 28 Sep 2016 20:46:37 GMT
WORKDIR /go
# Wed, 28 Sep 2016 20:46:37 GMT
COPY file:f6191f2c86edc9343569339f101facba47e886e33e29d70da6916ca6b1101a53 in /usr/local/bin/ 
# Wed, 28 Sep 2016 20:46:39 GMT
RUN mkdir -p /go/src/app
# Wed, 28 Sep 2016 20:46:39 GMT
WORKDIR /go/src/app
# Wed, 28 Sep 2016 20:46:44 GMT
CMD ["go-wrapper" "run"]
# Wed, 28 Sep 2016 20:46:44 GMT
ONBUILD COPY . /go/src/app
# Wed, 28 Sep 2016 20:46:45 GMT
ONBUILD RUN go-wrapper download
# Wed, 28 Sep 2016 20:46:45 GMT
ONBUILD RUN go-wrapper install
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
	-	`sha256:ff18e19c2db42055e6f34323700737bde3c819b413997cddace2c1b7180d7efd`  
		Last Modified: Fri, 23 Sep 2016 18:26:43 GMT  
		Size: 42.5 MB (42495967 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:00075397a1ec5875797c7916e5e28e4cf9e9212b9e129f3748e35018de80a0d0`  
		Last Modified: Wed, 28 Sep 2016 20:47:22 GMT  
		Size: 59.7 MB (59651226 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ee3cf1ce58d6e90f7624f5c64a14d3438ca977be21b63898e4845c5a7b9c8bd9`  
		Last Modified: Wed, 28 Sep 2016 20:50:34 GMT  
		Size: 81.6 MB (81629055 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:741206fcd3b82fdd13df155e2a584e9c75b831b3265eec5f9c63adf386d5ee2c`  
		Last Modified: Wed, 28 Sep 2016 20:50:08 GMT  
		Size: 123.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:369d69bdd76d578056ecf7b3580ff166ad1037fb3cb48138cf984ca8582367f0`  
		Last Modified: Wed, 28 Sep 2016 20:50:08 GMT  
		Size: 1.4 KB (1353 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c5b92bb7a7fc63dbcaa91024872adf00edebf28d45f5f15df92d308ca3ce2b6e`  
		Last Modified: Wed, 28 Sep 2016 20:51:24 GMT  
		Size: 132.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
