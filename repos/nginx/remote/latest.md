## `nginx:latest`

```console
$ docker pull nginx@sha256:d33834dd25d330da75dccd8add3ae2c9d7bb97f502b421b02cecb6cb7b34a1b6
```

-	Platforms:
	-	linux; amd64

### `nginx:latest` - linux; amd64

-	Docker Version: 1.10.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **71.4 MB (71413220 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:4efb2fcdb1ab05fb03c9435234343c1cc65289eeb016be86193e88d3a5d84f6b`
-	Default Command: `["nginx","-g","daemon off;"]`

```dockerfile
# Thu, 28 Jul 2016 17:47:54 GMT
ADD file:0e0565652aa852f62033d99f84892216020d30f64521ded5e72d4940bc4c9697 in /
# Thu, 28 Jul 2016 17:47:55 GMT
CMD ["/bin/bash"]
# Tue, 23 Aug 2016 18:49:31 GMT
MAINTAINER NGINX Docker Maintainers "docker-maint@nginx.com"
# Tue, 23 Aug 2016 18:49:33 GMT
ENV NGINX_VERSION=1.11.3-1~jessie
# Tue, 23 Aug 2016 18:51:19 GMT
RUN apt-key adv --keyserver hkp://pgp.mit.edu:80 --recv-keys 573BFD6B3D8FBC641079A6ABABF5BD827BD9BF62 	&& echo "deb http://nginx.org/packages/mainline/debian/ jessie nginx" >> /etc/apt/sources.list 	&& apt-get update 	&& apt-get install --no-install-recommends --no-install-suggests -y 						ca-certificates 						nginx=${NGINX_VERSION} 						nginx-module-xslt 						nginx-module-geoip 						nginx-module-image-filter 						nginx-module-perl 						nginx-module-njs 						gettext-base 	&& rm -rf /var/lib/apt/lists/*
# Tue, 23 Aug 2016 18:51:21 GMT
RUN ln -sf /dev/stdout /var/log/nginx/access.log 	&& ln -sf /dev/stderr /var/log/nginx/error.log
# Tue, 23 Aug 2016 18:51:22 GMT
EXPOSE 443/tcp 80/tcp
# Tue, 23 Aug 2016 18:51:23 GMT
CMD ["nginx" "-g" "daemon off;"]
```

-	Layers:
	-	`sha256:357ea8c3d80bc25792e010facfc98aee5972ebc47e290eb0d5aea3671a901cab`  
		Last Modified: Thu, 28 Jul 2016 17:49:58 GMT  
		Size: 51.4 MB (51365611 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0fc04568277e2ac7eeab8071421127677b1d912bec0ff7319cbfab5925c65179`  
		Last Modified: Tue, 23 Aug 2016 18:56:48 GMT  
		Size: 20.0 MB (20047416 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0bed9719ddcb355fb9220423d3dd9cd6c41d8e0be5f44580e3929da574db4530`  
		Last Modified: Tue, 23 Aug 2016 18:56:41 GMT  
		Size: 193.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip