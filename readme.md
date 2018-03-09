## Centmin Mod Nginx RPMs for CentOS 7.4+

CentOS 7.4+ 64bit only experimental Nginx 1.13.9 RPM builds for [Centmin Mod LEMP stack](https://centminmod.com) using 123.09beta01 branch Nginx compilation routines.

## Centmin Mod Nginx RPM Dependencies:

* jemalloc

```
yum -y install epel-release
yum -y install jemalloc
yum -y localinstall cmm-ngx-1.13.9-1.el7.x86_64.rpm
```

## Centmin Mod Nginx RPM Build Details

Built using GCC 7.2.1 compiler with persistent config file `/etc/centminmod/custom_config.inc` settings:

```
MARCH_TARGETNATIVE='n'
NGINX_VERSION='1.13.9'
OPENSSL_VERSION='1.1.0g'
NGINX_HPACK='y'
NGINX_DYNAMICTLS='y'
LIBRESSL_SWITCH='n'
CLANG='n'
DEVTOOLSETSEVEN='y'
NGINX_DEVTOOLSETGCC='y'
CLOUDFLARE_ZLIB='y'
CLOUDFLARE_ZLIBPHP='y'
NGXDYNAMIC_BROTLI='y'
NGINX_LIBBROTLI='y'
NGXDYNAMIC_GEOIP='y'
NGXDYNAMIC_STREAMGEOIP='y'
NGXDYNAMIC_STREAMREALIP='y'
NGXDYNAMIC_SRCCACHE='y'
NGXDYNAMIC_DEVELKIT='y'
NGXDYNAMIC_REDISTWO='y'
```

Nginx configuration


> ./configure --with-ld-opt="-L/usr/local/lib -ljemalloc -Wl,-z,relro -Wl,-rpath,/usr/local/lib" --with-cc-opt="-I/usr/local/include -m64 -march=x86-64 -g -O3 -Wno-error=strict-aliasing -fstack-protector-strong -flto -fuse-ld=gold --param=ssp-buffer-size=4 -Wformat -Werror=format-security -Wimplicit-fallthrough=0 -fcode-hoisting  -Wp,-D_FORTIFY_SOURCE=2 -Wno-deprecated-declarations -gsplit-dwarf" --sbin-path=/usr/local/sbin/nginx --conf-path=/usr/local/nginx/conf/nginx.conf --with-compat --with-http_stub_status_module --with-http_secure_link_module --with-libatomic --with-http_gzip_static_module --add-dynamic-module=../ngx_brotli --with-http_sub_module --with-http_addition_module --with-http_image_filter_module=dynamic --with-http_geoip_module=dynamic --with-stream_geoip_module=dynamic --with-stream_realip_module --with-stream_ssl_preread_module --with-threads --with-stream=dynamic --with-stream_ssl_module --with-http_realip_module --add-dynamic-module=../ngx-fancyindex-0.4.2 --add-module=../ngx_cache_purge-2.4.2 --add-dynamic-module=../ngx_devel_kit-0.3.0 --add-dynamic-module=../set-misc-nginx-module-0.31 --add-dynamic-module=../echo-nginx-module-0.61 --add-dynamic-module=../redis2-nginx-module-0.14 --add-module=../ngx_http_redis-0.3.7 --add-module=../memc-nginx-module-0.18 --add-dynamic-module=../srcache-nginx-module-0.31 --add-dynamic-module=../headers-more-nginx-module-0.33 --with-pcre=../pcre-8.41 --with-pcre-jit --with-zlib=../zlib-cloudflare-1.3.0 --with-http_ssl_module --with-http_v2_module --with-http_v2_hpack_enc --with-openssl=../openssl-1.1.0g --with-openssl-opt='enable-ec_nistp_64_gcc_128'


```
rpm -qpl --provides cmm-ngx-1.13.9-1.el7.x86_64.rpm
cmm-ngx(x86-64) = 1.13.9-1.el7
/etc/init.d/nginx
/usr/bin/nginxconf
/usr/bin/ngxreload
/usr/bin/ngxrestart
/usr/bin/ngxstart
/usr/bin/ngxstop
/usr/bin/statfilesinc
/usr/bin/vhostconf
/usr/local/nginx/client_body_temp
/usr/local/nginx/conf/503include-main.conf
/usr/local/nginx/conf/503include-only.conf
/usr/local/nginx/conf/autoprotect/demodomain.com/autoprotect-demodomain.com.conf
/usr/local/nginx/conf/block.conf
/usr/local/nginx/conf/blockbots.conf
/usr/local/nginx/conf/botlimit.conf
/usr/local/nginx/conf/cloudflare.conf
/usr/local/nginx/conf/cloudflare_customips.conf
/usr/local/nginx/conf/conf.d/demodomain.com.conf
/usr/local/nginx/conf/conf.d/virtual.conf
/usr/local/nginx/conf/drop.conf
/usr/local/nginx/conf/dynamic-modules-includes.conf
/usr/local/nginx/conf/dynamic-modules.conf
/usr/local/nginx/conf/errorpage.conf
/usr/local/nginx/conf/fastcgi.conf
/usr/local/nginx/conf/fastcgi.conf.default
/usr/local/nginx/conf/fastcgi_param_https_map.conf
/usr/local/nginx/conf/fastcgi_params
/usr/local/nginx/conf/fastcgi_params.default
/usr/local/nginx/conf/geoip.conf
/usr/local/nginx/conf/htpasswd
/usr/local/nginx/conf/htpasswd.py
/usr/local/nginx/conf/htpasswd.sh
/usr/local/nginx/conf/htpasswd_opcache
/usr/local/nginx/conf/include_opcache.conf
/usr/local/nginx/conf/koi-utf
/usr/local/nginx/conf/koi-win
/usr/local/nginx/conf/maintenance.conf
/usr/local/nginx/conf/mime.types
/usr/local/nginx/conf/mime.types.default
/usr/local/nginx/conf/nginx.conf
/usr/local/nginx/conf/nginx.conf.default
/usr/local/nginx/conf/pagespeed.conf
/usr/local/nginx/conf/pagespeedadmin.conf
/usr/local/nginx/conf/pagespeedhandler.conf
/usr/local/nginx/conf/pagespeedstatslog.conf
/usr/local/nginx/conf/php-pool2.conf
/usr/local/nginx/conf/php-pool3.conf
/usr/local/nginx/conf/php-pool4.conf
/usr/local/nginx/conf/php-pool5.conf
/usr/local/nginx/conf/php.conf
/usr/local/nginx/conf/phpalt.conf
/usr/local/nginx/conf/phpfpmd/phpfpm_pool2.conf
/usr/local/nginx/conf/phpfpmd/phpfpm_pool3.conf
/usr/local/nginx/conf/phpfpmd/phpfpm_pool4.conf
/usr/local/nginx/conf/phpfpmd/phpfpm_pool5.conf
/usr/local/nginx/conf/phpssl.conf
/usr/local/nginx/conf/phpstatus.conf
/usr/local/nginx/conf/proxy.conf
/usr/local/nginx/conf/pscontrol
/usr/local/nginx/conf/scgi_params
/usr/local/nginx/conf/scgi_params.default
/usr/local/nginx/conf/sitestatus.conf
/usr/local/nginx/conf/ssl/.gitignore
/usr/local/nginx/conf/ssl_include.conf
/usr/local/nginx/conf/staticfiles.conf
/usr/local/nginx/conf/uwsgi_params
/usr/local/nginx/conf/uwsgi_params.default
/usr/local/nginx/conf/vts_http.conf
/usr/local/nginx/conf/vts_mainserver.conf
/usr/local/nginx/conf/vts_server.conf
/usr/local/nginx/conf/webp.conf
/usr/local/nginx/conf/win-utf
/usr/local/nginx/conf/wpffpc.conf
/usr/local/nginx/fastcgi_temp
/usr/local/nginx/html/401.html
/usr/local/nginx/html/403.html
/usr/local/nginx/html/404.html
/usr/local/nginx/html/500.html
/usr/local/nginx/html/502.html
/usr/local/nginx/html/503.html
/usr/local/nginx/html/503.jpg
/usr/local/nginx/html/504.html
/usr/local/nginx/html/50x.html
/usr/local/nginx/html/cmlogo.png
/usr/local/nginx/html/geoip.php
/usr/local/nginx/html/index.html
/usr/local/nginx/html/maintenance.html
/usr/local/nginx/logs/nginx.pid
/usr/local/nginx/modules/ndk_http_module.so
/usr/local/nginx/modules/ngx_http_brotli_filter_module.so
/usr/local/nginx/modules/ngx_http_brotli_static_module.so
/usr/local/nginx/modules/ngx_http_echo_module.so
/usr/local/nginx/modules/ngx_http_fancyindex_module.so
/usr/local/nginx/modules/ngx_http_geoip_module.so
/usr/local/nginx/modules/ngx_http_headers_more_filter_module.so
/usr/local/nginx/modules/ngx_http_image_filter_module.so
/usr/local/nginx/modules/ngx_http_redis2_module.so
/usr/local/nginx/modules/ngx_http_set_misc_module.so
/usr/local/nginx/modules/ngx_http_srcache_filter_module.so
/usr/local/nginx/modules/ngx_stream_geoip_module.so
/usr/local/nginx/modules/ngx_stream_module.so
/usr/local/nginx/scgi_temp
/usr/local/nginx/uwsgi_temp
/usr/local/sbin/nginx
```