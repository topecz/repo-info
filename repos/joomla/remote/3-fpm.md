## `joomla:3-fpm`

```console
$ docker pull joomla@sha256:9e4053252228eac989c5bb6ed8622e378fcb266c1a579ab153fbb2c302ef28fc
```

-	Platforms:
	-	linux; amd64

### `joomla:3-fpm` - linux; amd64

-	Docker Version: 1.12.1
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **161.6 MB (161646534 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:ba32a696ba72279e0a63ab5d528efdc75412e48f1f57cf40c2725dfa59dec626`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["php-fpm"]`

```dockerfile
# Fri, 23 Sep 2016 18:08:50 GMT
ADD file:c6c23585ab140b0b320d4e99bc1b0eb544c9e96c24d90fec5e069a6d57d335ca in / 
# Fri, 23 Sep 2016 18:08:51 GMT
CMD ["/bin/bash"]
# Fri, 23 Sep 2016 21:19:23 GMT
ENV PHPIZE_DEPS=autoconf 		file 		g++ 		gcc 		libc-dev 		make 		pkg-config 		re2c
# Fri, 23 Sep 2016 21:19:52 GMT
RUN apt-get update && apt-get install -y 		$PHPIZE_DEPS 		ca-certificates 		curl 		libedit2 		libsqlite3-0 		libxml2 		xz-utils 	--no-install-recommends && rm -r /var/lib/apt/lists/*
# Fri, 23 Sep 2016 21:19:53 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Fri, 23 Sep 2016 21:19:53 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Fri, 23 Sep 2016 21:28:05 GMT
ENV PHP_EXTRA_CONFIGURE_ARGS=--enable-fpm --with-fpm-user=www-data --with-fpm-group=www-data
# Fri, 23 Sep 2016 21:28:05 GMT
ENV GPG_KEYS=0BD78B5F97500D450838F95DFE857D9A90D90EC1 6E4F6AB321FDC07F2C332E3AC2BF0BC433CFC8B3
# Fri, 23 Sep 2016 21:28:05 GMT
ENV PHP_VERSION=5.6.26
# Fri, 23 Sep 2016 21:28:06 GMT
ENV PHP_FILENAME=php-5.6.26.tar.xz
# Fri, 23 Sep 2016 21:28:06 GMT
ENV PHP_SHA256=203a854f0f243cb2810d1c832bc871ff133eccdf1ff69d32846f93bc1bef58a8
# Fri, 23 Sep 2016 21:28:10 GMT
RUN set -xe 	&& cd /usr/src 	&& curl -fSL "https://secure.php.net/get/$PHP_FILENAME/from/this/mirror" -o php.tar.xz 	&& echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c - 	&& curl -fSL "https://secure.php.net/get/$PHP_FILENAME.asc/from/this/mirror" -o php.tar.xz.asc 	&& export GNUPGHOME="$(mktemp -d)" 	&& for key in $GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	done 	&& gpg --batch --verify php.tar.xz.asc php.tar.xz 	&& rm -r "$GNUPGHOME"
# Fri, 23 Sep 2016 21:28:10 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Fri, 23 Sep 2016 21:31:34 GMT
RUN set -xe 	&& buildDeps=" 		$PHP_EXTRA_BUILD_DEPS 		libcurl4-openssl-dev 		libedit-dev 		libsqlite3-dev 		libssl-dev 		libxml2-dev 	" 	&& apt-get update && apt-get install -y $buildDeps --no-install-recommends && rm -rf /var/lib/apt/lists/* 		&& docker-php-source extract 	&& cd /usr/src/php 	&& ./configure 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--disable-cgi 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j"$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -executable -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& docker-php-source delete 		&& apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false $buildDeps
# Fri, 23 Sep 2016 21:31:35 GMT
COPY multi:ed54b4fe7bef284934703fa6e979b7cc0daed0549a07586d0c1ccd4e2b41884a in /usr/local/bin/ 
# Fri, 23 Sep 2016 21:31:35 GMT
WORKDIR /var/www/html
# Fri, 23 Sep 2016 21:31:36 GMT
RUN set -ex 	&& cd /usr/local/etc 	&& if [ -d php-fpm.d ]; then 		sed 's!=NONE/!=!g' php-fpm.conf.default | tee php-fpm.conf > /dev/null; 		cp php-fpm.d/www.conf.default php-fpm.d/www.conf; 	else 		mkdir php-fpm.d; 		cp php-fpm.conf.default php-fpm.d/www.conf; 		{ 			echo '[global]'; 			echo 'include=etc/php-fpm.d/*.conf'; 		} | tee php-fpm.conf; 	fi 	&& { 		echo '[global]'; 		echo 'error_log = /proc/self/fd/2'; 		echo; 		echo '[www]'; 		echo '; if we send this to /proc/self/fd/1, it never appears'; 		echo 'access.log = /proc/self/fd/2'; 		echo; 		echo 'clear_env = no'; 		echo; 		echo '; Ensure worker stdout and stderr are sent to the main error log.'; 		echo 'catch_workers_output = yes'; 	} | tee php-fpm.d/docker.conf 	&& { 		echo '[global]'; 		echo 'daemonize = no'; 		echo; 		echo '[www]'; 		echo 'listen = [::]:9000'; 	} | tee php-fpm.d/zz-docker.conf
# Fri, 23 Sep 2016 21:31:36 GMT
EXPOSE 9000/tcp
# Fri, 23 Sep 2016 21:31:37 GMT
CMD ["php-fpm"]
# Sat, 24 Sep 2016 03:59:30 GMT
MAINTAINER Michael Babker <michael.babker@joomla.org> (@mbabker)
# Sat, 24 Sep 2016 03:59:51 GMT
RUN apt-get update && apt-get install -y libpng12-dev libjpeg-dev zip unzip && rm -rf /var/lib/apt/lists/* 	&& docker-php-ext-configure gd --with-png-dir=/usr --with-jpeg-dir=/usr 	&& docker-php-ext-install gd
# Sat, 24 Sep 2016 03:59:58 GMT
RUN docker-php-ext-install mysqli
# Sat, 24 Sep 2016 03:59:59 GMT
VOLUME [/var/www/html]
# Sat, 24 Sep 2016 03:59:59 GMT
ENV JOOMLA_VERSION=3.6.2
# Sat, 24 Sep 2016 03:59:59 GMT
ENV JOOMLA_SHA1=fdaa25337aaabd0d673aafc0ff90e7375de2d6e3
# Sat, 24 Sep 2016 04:00:06 GMT
RUN curl -o joomla.zip -SL https://github.com/joomla/joomla-cms/releases/download/${JOOMLA_VERSION}/Joomla_${JOOMLA_VERSION}-Stable-Full_Package.zip 	&& echo "$JOOMLA_SHA1 *joomla.zip" | sha1sum -c - 	&& mkdir /usr/src/joomla 	&& unzip joomla.zip -d /usr/src/joomla 	&& rm joomla.zip 	&& chown -R www-data:www-data /usr/src/joomla
# Sat, 24 Sep 2016 04:00:07 GMT
COPY file:27ca5c0b8509d6681e80aa6cd05b2e2e68da2f59fb0ee7fa2aa581f55d362b6d in /entrypoint.sh 
# Sat, 24 Sep 2016 04:00:07 GMT
COPY file:7328ebe063e26f7b7716dfd8778bb7d46b90702ea38b23b9147ba2fd837ac2c1 in /makedb.php 
# Sat, 24 Sep 2016 04:00:08 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Sat, 24 Sep 2016 04:00:08 GMT
CMD ["php-fpm"]
```

-	Layers:
	-	`sha256:6a5a5368e0c2d3e5909184fa28ddfd56072e7ff3ee9a945876f7eee5896ef5bb`  
		Last Modified: Fri, 23 Sep 2016 18:10:19 GMT  
		Size: 51.4 MB (51354364 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:de059afc6b5da83892f482eea8b08dc72f8fbe69282c72b533116f1dd3689426`  
		Last Modified: Fri, 23 Sep 2016 21:23:50 GMT  
		Size: 77.6 MB (77592141 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9b1ac0143753de213aff9a45bb2b68b28a437ec3f015efa7f35622491d5c06ff`  
		Last Modified: Fri, 23 Sep 2016 21:23:27 GMT  
		Size: 179.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2ce19e16f61bc6e5320c327d66037ddc770407e95eb60cbfe7ee9b33aa9ca65e`  
		Last Modified: Fri, 23 Sep 2016 21:31:48 GMT  
		Size: 12.4 MB (12417481 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8f7ab14322501cde225129bf89e96566577bd5d278c6a60ea7dd864c1d6cfcd7`  
		Last Modified: Fri, 23 Sep 2016 21:31:44 GMT  
		Size: 490.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:21e7e9616671c2689898d27c6f61b07dd1f82c6b7172da42ba57f5890986a356`  
		Last Modified: Fri, 23 Sep 2016 21:31:47 GMT  
		Size: 8.8 MB (8834935 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9a4bff2cb766be3ed6a23d4963605068e7ea8f95adfb8fd636410b3534feb02d`  
		Last Modified: Fri, 23 Sep 2016 21:31:44 GMT  
		Size: 1.8 KB (1831 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:23a14705c2152ba673f5a6c8c32354c6733c9aeebaf8ad76887ea1bb3ad72a56`  
		Last Modified: Fri, 23 Sep 2016 21:31:44 GMT  
		Size: 129.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4ab3ee32b4c623bace5e3954243fdac94e551b5e4be02ada8e7c19b82a1d4882`  
		Last Modified: Fri, 23 Sep 2016 21:31:44 GMT  
		Size: 7.6 KB (7629 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fe393d1d4aa1f0df1a5839ce92ace664bc35e054fdf6afb885f599b49ad81a35`  
		Last Modified: Sat, 24 Sep 2016 04:00:17 GMT  
		Size: 2.8 MB (2817556 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:aaf3aeb6e7e2feb5d45c5c0f804cf2f53380f83430aea8244f37d80a77a8b1fd`  
		Last Modified: Sat, 24 Sep 2016 04:00:16 GMT  
		Size: 266.1 KB (266130 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0cb8c34dfe8653f5625b10e71b9478874e1633197b3db28b0c2870c4b80bcc29`  
		Last Modified: Sat, 24 Sep 2016 04:00:20 GMT  
		Size: 8.4 MB (8351899 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:507d74bf0302b59f7c45abf815525eaeaea5338e462379607b92ab1204407914`  
		Last Modified: Sat, 24 Sep 2016 04:00:16 GMT  
		Size: 1.2 KB (1164 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:45bce082b192b48963d6f13654dd13ac6b01e237aa692db533fca798a092de42`  
		Last Modified: Sat, 24 Sep 2016 04:00:16 GMT  
		Size: 606.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
