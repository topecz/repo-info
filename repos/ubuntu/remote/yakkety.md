## `ubuntu:yakkety`

```console
$ docker pull ubuntu@sha256:c09fdd98c2344f9df4617716da49cdf27d1bb31651eaad81b20b795e1e206ab8
```

-	Platforms:
	-	linux; amd64

### `ubuntu:yakkety` - linux; amd64

-	Docker Version: 1.12.1
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **40.0 MB (40038524 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:ad8ee902e9bbe18dc665ae2df0dafe41b82c508b7cbaf76d086357034ba755f3`
-	Default Command: `["\/bin\/bash"]`

```dockerfile
# Mon, 26 Sep 2016 21:26:33 GMT
ADD file:b16a2598f26dcaf5b699043a8672a58b3d1afbd40fce3a8a6f73c3a7cfa45069 in / 
# Mon, 26 Sep 2016 21:26:34 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Mon, 26 Sep 2016 21:26:35 GMT
RUN rm -rf /var/lib/apt/lists/*
# Mon, 26 Sep 2016 21:26:36 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Mon, 26 Sep 2016 21:26:37 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Mon, 26 Sep 2016 21:26:37 GMT
CMD ["/bin/bash"]
```

-	Layers:
	-	`sha256:9c46ca5bd675a982eac520bfe2b3a2cae2537518a8b147f2e32d7cbfb8130ca0`  
		Last Modified: Mon, 26 Sep 2016 21:30:07 GMT  
		Size: 40.0 MB (40036283 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d014607c89b6d7ffb531230dd6330c4f6bbf89e934f929d96bd731eab565d37b`  
		Last Modified: Mon, 26 Sep 2016 21:29:53 GMT  
		Size: 823.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2f58d27ed26992577ea3682a38eb8208619992bbe8fb09a13ca9515a18f7862d`  
		Last Modified: Mon, 26 Sep 2016 21:29:53 GMT  
		Size: 392.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:435d3c68bf548af28ba111ab32c9c138bb7eb2dcc0e5dc492884218c3f94465c`  
		Last Modified: Mon, 26 Sep 2016 21:29:53 GMT  
		Size: 864.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d3b3cf1bddf912faad94f67f5878101ca86a7dddc0a395c863784a946da683a7`  
		Last Modified: Mon, 26 Sep 2016 21:29:52 GMT  
		Size: 162.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
