# Apache

usage: **\`\`\`apache**

renders:

```apache
AddDefaultCharset UTF-8

RewriteEngine On

# Serve gzipped version if available and accepted
AddEncoding x-gzip .gz
RewriteCond %{HTTP:Accept-Encoding} gzip
RewriteCond %{REQUEST_FILENAME}.gz -f
RewriteRule ^(.*)$ $1.gz [QSA,L]
<FilesMatch \.css\.gz$>
  ForceType text/css
  Header append Vary Accept-Encoding
</FilesMatch>
<FilesMatch \.js\.gz$>
  ForceType application/javascript
  Header append Vary Accept-Encoding
</FilesMatch>
<FilesMatch \.html\.gz$>
  ForceType text/html
  Header append Vary Accept-Encoding
</FilesMatch>
```
