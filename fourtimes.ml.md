### Configure nginx

```bash
vi /etc/nginx/sites-available/fourtimes.ml

add this content:
-----------------
server {
    listen       80;
    server_name  fourtimes.ml;
    access_log /var/log/nginx/fourtimes.ml.access.log;
    error_log  /var/log/nginx/fourtimes.ml.error.log;

    location / {
        root   /var/www/fourtimes.ml;
        index  index.html index.htm;
    }
}
```

**create directory file**

```bash
mkdir /var/www/fourtimes.ml
```

**change the directory**

```bash
cd /etc/nginx/sites-enabled
```

**copy the file sites-enabled from site-available**

```bash
ln -s /etc/nginx/sites-available/fourtimes.ml ./
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
vim /var/www/fourtimes.ml/index.html

add this content:
-----------------
<html>
<body>
<div style="width: 100%; font-size: 40px; font-weight: bold; text-ign: center;">
welcome to the fourtimes.ml domain
</div>
</body>
</html>
```

**Enter into the ip and domain name in /etc/hosts**

```bash
vim /etc/hosts

ip address    domain name
192.168.94.83 fourtimes.ml
```

**To run inside the termin**

```bash
curl fourtimes.ml
```

**Output**

![image](https://user-images.githubusercontent.com/91359308/169755460-d5a6789d-2c0d-4de7-bb12-197e04ccdbb2.png)

