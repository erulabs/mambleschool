# Seandon Mooy's static blog project

My homepage! See http://seandonmooy.com (and also http://erulabs.com)

Features:
  - Totally static blog (serve from s3 bucket, github pages, etc!)
  - Jade for writing posts
  - very simple!

todos:
  Disqus for comments on posts
  twitter/facebook icons on blog posts
  make homepage video scale better (no borders)

thanks to:
  http://coverr.co/ for the background video

An example NGINX config for this project - note that the only important thing is that all requests are redirected to index.html

```
server {
  charset utf-8;
  etag on;
  expires 1w;

  location ~* \.(png|otf|eot|svg|ttf|woff|woff2|gif|jpg|jpeg|js|css)$ {
    add_header Cache-Control 'public';
    access_log off;
  }
  location / {
    try_files $uri /index.html;
  }
}
```
