# backblaze + cloudflare file hoster

## setup instructions
 
### this webapp

- create backblaze bucket
- set bucket to public
- create an application key for bucket
- create config.php from config.example.php
- run `composer install`

### cloudflare cname

- set to backblaze specific endpoint domain e.g. s3.us-east-005.backblazeb2.com

### cloudflare transform rules

Name: B2 Rewrite rule
When incoming requests match…
Enter the following:
Field:Hostname Operator:equals Value:[your domain name ex files.stumb.org]
Path:
Select: Rewrite to...
Select: Dynamic
Enter: concat("/file/[your bucket name here e.g. stumbfiles]", http.request.uri.path)
