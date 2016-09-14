## `chronograf:latest`

```console
$ docker pull chronograf@sha256:51c6760e802c9e47d042562440396fc2f598ec7fbda88d818fe29972779a753c
```

-	Platforms:
	-	linux; amd64

### `chronograf:latest` - linux; amd64

-	Docker Version: 1.12.1
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **73.9 MB (73902869 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:a397f5ac08de2d987f354330c0a2d6e92c4134f79b3e2126dce5d875b32ed69f`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["chronograf"]`

```dockerfile
# Tue, 30 Aug 2016 21:00:51 GMT
ADD file:f2453b914e7e026efd39c6321c7b14509b6d09dd3cf5567a8f6bd38466e06954 in / 
# Tue, 30 Aug 2016 21:00:52 GMT
CMD ["/bin/bash"]
# Tue, 30 Aug 2016 21:52:11 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 30 Aug 2016 21:58:18 GMT
RUN gpg     --keyserver hkp://ha.pool.sks-keyservers.net     --recv-keys 05CE15085FC09D18E99EFB22684A14CF2582E0C5
# Wed, 31 Aug 2016 01:16:11 GMT
ENV CHRONOGRAF_VERSION=0.13.0
# Wed, 31 Aug 2016 01:16:12 GMT
RUN wget -q https://dl.influxdata.com/chronograf/releases/chronograf_${CHRONOGRAF_VERSION}_amd64.deb.asc &&     wget -q https://dl.influxdata.com/chronograf/releases/chronograf_${CHRONOGRAF_VERSION}_amd64.deb &&     gpg --batch --verify chronograf_${CHRONOGRAF_VERSION}_amd64.deb.asc chronograf_${CHRONOGRAF_VERSION}_amd64.deb &&     dpkg -i chronograf_${CHRONOGRAF_VERSION}_amd64.deb &&     rm -f chronograf_${CHRONOGRAF_VERSION}_amd64.deb*
# Wed, 31 Aug 2016 01:16:13 GMT
COPY file:6bd8f62167b75e75bb429d6dda670ec917256913ff3370f929e2c8d9e14b475e in /etc/chronograf/chronograf.conf 
# Wed, 31 Aug 2016 01:16:13 GMT
EXPOSE 10000/tcp
# Wed, 31 Aug 2016 01:16:13 GMT
ENV PATH=/opt/chronograf:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Wed, 31 Aug 2016 01:16:13 GMT
VOLUME [/var/lib/chronograf]
# Wed, 31 Aug 2016 01:16:14 GMT
COPY file:fc95049005144e726efe031fc5e003a8eedf95c50f0041c41c3161e64cf9dbbe in /entrypoint.sh 
# Wed, 31 Aug 2016 01:16:14 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Wed, 31 Aug 2016 01:16:14 GMT
CMD ["chronograf"]
```

-	Layers:
	-	`sha256:8ad8b3f87b378cfae583fef34e47a3c9203847d779961b7351cbf786af0bc09f`  
		Last Modified: Tue, 30 Aug 2016 21:02:02 GMT  
		Size: 51.4 MB (51367268 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:751fe39c4d348c7fc411d46929c1dac390e3d7107efc9f8f69641b50e14459f7`  
		Last Modified: Tue, 30 Aug 2016 21:59:08 GMT  
		Size: 18.5 MB (18527264 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4cb171ee4d0b36bdbf042b750841ac151b30674348314de3d762aeeaaf3d69bb`  
		Last Modified: Tue, 30 Aug 2016 21:59:05 GMT  
		Size: 6.8 KB (6753 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7ca8422c9e72d0c9149d905238a4f6abb983f97823278501e4f75670b91f0eec`  
		Last Modified: Wed, 07 Sep 2016 21:45:43 GMT  
		Size: 4.0 MB (4001192 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:449caa9384e53c741f6bc90a5076e8691dfa3b63ca5a8ae03db72485c3733076`  
		Last Modified: Wed, 07 Sep 2016 21:45:41 GMT  
		Size: 205.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e9fd596fa8c1343d49f9d218a48d1d4353db0b93485952adc106dc36ee27afe7`  
		Last Modified: Wed, 07 Sep 2016 21:45:40 GMT  
		Size: 187.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip