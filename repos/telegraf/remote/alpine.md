## `telegraf:alpine`

```console
$ docker pull telegraf@sha256:b425d1f8a646f2d4061689f4f741368c5fb5d9e37428e3e8defb940a74070fd6
```

-	Platforms:
	-	linux; amd64

### `telegraf:alpine` - linux; amd64

-	Docker Version: 1.12.1
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **10.1 MB (10144842 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:f6cd36842ae6557230d065ac4a4999d8352aaad63c8704bee4bb83460b1491a7`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["telegraf"]`

```dockerfile
# Fri, 23 Sep 2016 16:29:57 GMT
ADD file:d6ee3ba7a4d59b161917082cc7242c660c61bb3f3cc1549c7e2dfff2b0de7104 in / 
# Fri, 23 Sep 2016 18:37:37 GMT
ENV TELEGRAF_VERSION=1.0.0
# Fri, 23 Sep 2016 18:37:45 GMT
RUN apk add --no-cache --virtual .build-deps wget gnupg tar ca-certificates &&     update-ca-certificates &&     gpg --keyserver hkp://ha.pool.sks-keyservers.net         --recv-keys 05CE15085FC09D18E99EFB22684A14CF2582E0C5 &&     wget -q https://dl.influxdata.com/telegraf/releases/telegraf-${TELEGRAF_VERSION}-static_linux_amd64.tar.gz.asc &&     wget -q https://dl.influxdata.com/telegraf/releases/telegraf-${TELEGRAF_VERSION}-static_linux_amd64.tar.gz &&     gpg --batch --verify telegraf-${TELEGRAF_VERSION}-static_linux_amd64.tar.gz.asc telegraf-${TELEGRAF_VERSION}-static_linux_amd64.tar.gz &&     mkdir -p /usr/src /etc/telegraf &&     tar -C /usr/src -xzf telegraf-${TELEGRAF_VERSION}-static_linux_amd64.tar.gz &&     mv /usr/src/telegraf*/telegraf.conf /etc/telegraf/ &&     chmod +x /usr/src/telegraf*/* &&     cp -a /usr/src/telegraf*/* /usr/bin/ &&     rm -rf *.tar.gz* /usr/src /root/.gnupg &&     apk del .build-deps
# Fri, 23 Sep 2016 18:37:46 GMT
EXPOSE 8092/udp 8094/tcp 8125/udp
# Fri, 23 Sep 2016 18:37:46 GMT
COPY file:43e6828e001b57ab465cff8dfd3d30830289afe7ca5944b61641956bfe38cd1c in /entrypoint.sh 
# Fri, 23 Sep 2016 18:37:46 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Fri, 23 Sep 2016 18:37:47 GMT
CMD ["telegraf"]
```

-	Layers:
	-	`sha256:c0cb142e43453ebb1f82b905aa472e6e66017efd43872135bc5372e4fac04031`  
		Last Modified: Fri, 23 Sep 2016 16:30:54 GMT  
		Size: 2.3 MB (2312930 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5eddae206c8b4e2d0fb46f401dda137d93c71938ca5b6385eb93a96e8a6286ff`  
		Last Modified: Fri, 23 Sep 2016 18:37:57 GMT  
		Size: 7.8 MB (7831733 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3a23d0e2d033f4f38c4581e98ad19e4a38454ea4d497fd1a7c80576e73b41b89`  
		Last Modified: Fri, 23 Sep 2016 18:37:54 GMT  
		Size: 179.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
