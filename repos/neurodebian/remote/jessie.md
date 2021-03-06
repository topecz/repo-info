## `neurodebian:jessie`

```console
$ docker pull neurodebian@sha256:a29107b1e9df310d567aff987fda03ac5ad167e22834dca8027049dc673356c7
```

-	Platforms:
	-	linux; amd64

### `neurodebian:jessie` - linux; amd64

-	Docker Version: 1.12.1
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **51.4 MB (51358204 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:e734160d3b3a0f89ecbaa709d650bba277bf1cf9d38f45c75e7776c50f090852`
-	Default Command: `["\/bin\/bash"]`

```dockerfile
# Fri, 23 Sep 2016 18:08:50 GMT
ADD file:c6c23585ab140b0b320d4e99bc1b0eb544c9e96c24d90fec5e069a6d57d335ca in / 
# Fri, 23 Sep 2016 18:08:51 GMT
CMD ["/bin/bash"]
# Fri, 23 Sep 2016 20:49:05 GMT
RUN which gpg || { apt-get update && apt-get install -y --no-install-recommends gnupg dirmngr && rm -rf /var/lib/apt/lists/*; }
# Fri, 23 Sep 2016 20:49:06 GMT
RUN echo 'deb http://neuro.debian.net/debian jessie main' > /etc/apt/sources.list.d/neurodebian.sources.list
# Fri, 23 Sep 2016 20:49:06 GMT
RUN echo 'deb http://neuro.debian.net/debian data main' >> /etc/apt/sources.list.d/neurodebian.sources.list
# Fri, 23 Sep 2016 20:49:07 GMT
RUN echo '#deb-src http://neuro.debian.net/debian-devel jessie main' >> /etc/apt/sources.list.d/neurodebian.sources.list
# Fri, 23 Sep 2016 20:49:08 GMT
RUN apt-key adv --recv-keys --keyserver pgp.mit.edu 0xA5D32F012649A5A9
```

-	Layers:
	-	`sha256:6a5a5368e0c2d3e5909184fa28ddfd56072e7ff3ee9a945876f7eee5896ef5bb`  
		Last Modified: Fri, 23 Sep 2016 18:10:19 GMT  
		Size: 51.4 MB (51354364 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:35030452da95817043071c08285ec55c6caef93013fabdc9bc501901ae1d8532`  
		Last Modified: Fri, 23 Sep 2016 20:49:16 GMT  
		Size: 214.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:91b00bf8773afc235e7c75f015c1117d4f1217f7d3ad34c852838e1d761d5931`  
		Last Modified: Fri, 23 Sep 2016 20:49:16 GMT  
		Size: 221.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b2010075f25befecf9840b6017b016595b9283a0f5ae96425c17daac90e44877`  
		Last Modified: Fri, 23 Sep 2016 20:49:16 GMT  
		Size: 238.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f453478092aa83c134bafbfa060b741ab595e6109e7071caf77b011177b0132e`  
		Last Modified: Fri, 23 Sep 2016 20:49:16 GMT  
		Size: 3.2 KB (3167 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
