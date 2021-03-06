### Configure nginx
```bash
vi /etc/nginx/sites-available/api.fourtimes.ml

add this content:
-----------------
server {
    listen       80;
    server_name  api.fourtimes.ml;
    access_log /var/log/nginx/api.fourtimes.ml.access.log;
    error_log  /var/log/nginx/api.fourtimes.ml.error.log;

    location / {
        root   /var/www/api.fourtimes.ml;
        index  index.html index.htm;
    }
}
```

**create directory file**

```bash
mkdir /var/www/api.fourtimes.ml
```

**change the directory**

```bash
cd /etc/nginx/sites-enabled
```
**copy the file sites-enabled from site-available**
```bash
ln -s /etc/nginx/sites-available/api.fourtimes.ml ./
```

**restart the server**

```bash
systemctl restart nginx
```
**status of the server**
```bash
systemctl status nginx
```
**Create index.html file and put the information:**
```bash
vim /var/www/api.fourtimes.ml/index.html

add this content:
-----------------
<html>
<body>
<div style="width: 100%; font-size: 40px; font-weight: bold; text-apiign: center;">
welcome to the api.fourtimes.ml domain
</div>
</body>
</html>
```
**Enter into the ip and domain name in /etc/hosts**
```bash
vim /etc/hosts

ip address    domain name
192.168.94.83 api.fourtimes.ml
```
**To run inside the terminapi**
```bash
curl api.fourtimes.ml
```

**Output**

![image](https://user-images.githubusercontent.com/91359308/169755707-447ed51c-227e-487d-81a1-1af680b599b5.png)
