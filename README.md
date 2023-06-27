# Custom domain cho Jetpack Photon (Webinoly)
Tạo subdomain i0.bibica.net thay thế cho i0.wp.com/cdn.bibica.net/wp-content/uploads bằng simple dedicated reverse proxy
```shell
sudo site i0.bibica.net -proxy=[https://i0.wp.com/cdn.bibica.net/wp-content/uploads/] -dedicated-reverse-proxy=simple
```
Sử dụng nginx_substitutions_filter để tự đổi các link i0.wp.com/cdn.bibica.net/wp-content/uploads -> i0.bibica.net trong bài viết
```shell
sub_filter_once off;
sub_filter_last_modified on;
sub_filter https://i0.wp.com/cdn.bibica.net/wp-content/uploads/ https://i0.bibica.net/;
```
