## Centmin Mod Nginx RPMs for CentOS 7.9

CentOS 7.9 64bit only experimental Nginx 1.21.6 RPM builds for [Centmin Mod LEMP stack](https://centminmod.com) using 130.00beta01 branch Nginx compilation routines. The custom RPM doesn't include Centmin Mod Nginx specific modified files, those are applied after Nginx RPM is installed via the normal Centmin Mod initial install routines.

## Centmin Mod Nginx RPM Dependencies:

Centmin Mod Nginx is built using alternative memory allocator, jemalloc instead of system default glibc malloc memory allocator.

```
yum -y install epel-release
yum -y install jemalloc jemalloc-devel
yum -y localinstall nginx-custom-1.21.6-1.el7.x86_64.rpm
```

## Centmin Mod Nginx RPM Build Details

Built using GCC 10.2 compiler with persistent config file `/etc/centminmod/custom_config.inc` settings:

```
MARCH_TARGETNATIVE='n'
NGINX_VERSION='1.21.6'
NGINX_HPACK='y'
NGINX_DYNAMICTLS='y'
DEVTOOLSETTEN='y'
NGINX_DEVTOOLSETGCC='y'
CLOUDFLARE_ZLIB='y'
NGINX_LIBBROTLI='y'
NGXDYNAMIC_BROTLI='y'
NGINX_NJS='y'
NGXDYNAMIC_NJS='y'
```

Nginx configuration

```
nginx -V
nginx version: nginx/1.21.6 (110622-045817-centos7-116155b-br-6e975bc)                                                                                                                                       built by gcc 10.2.1 20210130 (Red Hat 10.2.1-11) (GCC) 
built with OpenSSL 1.1.1o  3 May 2022
TLS SNI support enabled
```
> configure arguments: --with-ld-opt='-Wl,-E -L/usr/local/zlib-cf/lib -L/usr/local/nginx-dep/lib -ljemalloc -Wl,-z,relro -Wl,-rpath,/usr/local/zlib-cf/lib:/usr/local/nginx-dep/lib -fuse-ld=gold' --with-cc-opt='-I/usr/local/zlib-cf/include -I/usr/local/nginx-dep/include -m64 -march=x86-64 -mavx -mavx2 -mpclmul -msse4 -msse4.1 -msse4.2 -DTCP_FASTOPEN=23 -falign-functions=32 -g -O3 -Wno-strict-aliasing -fstack-protector-strong -fuse-ld=gold --param=ssp-buffer-size=4 -Wformat -Werror=format-security -Wno-pointer-sign -Wimplicit-fallthrough=0 -Wno-missing-profile -Wno-implicit-function-declaration -Wno-int-conversion -Wno-unused-result -Wno-unused-result -fcode-hoisting -Wp,-D_FORTIFY_SOURCE=2 -Wno-deprecated-declarations' --sbin-path=/usr/local/sbin/nginx --conf-path=/usr/local/nginx/conf/nginx.conf --build=110622-045817-centos7-116155b-br-6e975bc --with-compat --without-pcre2 --with-http_auth_request_module --with-http_stub_status_module --with-http_secure_link_module --with-http_flv_module --with-http_mp4_module --add-module=../nginx-rtmp-module --add-dynamic-module=../nginx-module-vts --with-libatomic --with-http_gzip_static_module --add-dynamic-module=../ngx_brotli --add-dynamic-module=../ngx_http_geoip2_module --with-http_sub_module --with-http_addition_module --with-http_image_filter_module=dynamic --with-http_geoip_module --add-dynamic-module=../njs/nginx --with-stream_geoip_module --with-stream_realip_module --with-stream_ssl_preread_module --with-threads --with-stream --with-stream_ssl_module --with-http_slice_module --with-http_realip_module --add-dynamic-module=../ngx-fancyindex-0.4.2 --add-module=../ngx_cache_purge-2.5.1 --add-dynamic-module=../ngx_devel_kit-0.3.0 --add-dynamic-module=../set-misc-nginx-module-0.32 --add-dynamic-module=../echo-nginx-module-0.62 --add-module=../redis2-nginx-module-0.15 --add-module=../ngx_http_redis-0.3.7 --add-module=../memc-nginx-module-0.19 --add-module=../srcache-nginx-module-0.32 --add-dynamic-module=../headers-more-nginx-module-0.33 --with-pcre-jit --with-zlib=../zlib-cloudflare-1.3.0 --with-http_ssl_module --with-http_v2_module --with-http_v2_hpack_enc --with-openssl=../openssl-1.1.1o --with-openssl-opt='enable-ec_nistp_64_gcc_128'

```
rpm -qpl /svr-setup/nginx-custom-1.21.6-1.el7.x86_64.rpm
/etc/systemd/system/nginx.service.d/failure-restart.conf
/etc/systemd/system/nginx.service.d/openfileslimit.conf
/usr/lib/systemd/system/nginx.service
/usr/local/nginx/conf/fastcgi.conf
/usr/local/nginx/conf/fastcgi.conf.default
/usr/local/nginx/conf/fastcgi_params
/usr/local/nginx/conf/fastcgi_params.default
/usr/local/nginx/conf/koi-utf
/usr/local/nginx/conf/koi-win
/usr/local/nginx/conf/mime.types
/usr/local/nginx/conf/mime.types.default
/usr/local/nginx/conf/nginx.conf
/usr/local/nginx/conf/nginx.conf.default
/usr/local/nginx/conf/scgi_params
/usr/local/nginx/conf/scgi_params.default
/usr/local/nginx/conf/uwsgi_params
/usr/local/nginx/conf/uwsgi_params.default
/usr/local/nginx/conf/win-utf
/usr/local/nginx/html/50x.html
/usr/local/nginx/html/index.html
/usr/local/nginx/logs
/usr/local/nginx/modules/ndk_http_module.so
/usr/local/nginx/modules/ngx_http_brotli_filter_module.so
/usr/local/nginx/modules/ngx_http_brotli_static_module.so
/usr/local/nginx/modules/ngx_http_echo_module.so
/usr/local/nginx/modules/ngx_http_fancyindex_module.so
/usr/local/nginx/modules/ngx_http_geoip2_module.so
/usr/local/nginx/modules/ngx_http_headers_more_filter_module.so
/usr/local/nginx/modules/ngx_http_image_filter_module.so
/usr/local/nginx/modules/ngx_http_js_module.so
/usr/local/nginx/modules/ngx_http_set_misc_module.so
/usr/local/nginx/modules/ngx_http_vhost_traffic_status_module.so
/usr/local/nginx/modules/ngx_stream_geoip2_module.so
/usr/local/nginx/modules/ngx_stream_js_module.so
/usr/local/sbin/nginx
```