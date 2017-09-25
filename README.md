# Goss
Goss



`# goss autoadd nginx`
```
Adding Group to './goss.yaml':
```

- nginx.yaml
```
package:
  nginx:
    installed: true
    versions:
    - 1.10.3
port:
  tcp:80:
    listening: true
    ip:
    - 0.0.0.0
  tcp:443:
    listening: true
    ip:
    - 0.0.0.0
  tcp6:80:
    listening: true
    ip:
    - '::'
service:
  nginx:
    enabled: true
    running: false
user:
  nginx:
    exists: true
    uid: 498
    gid: 497
    groups:
    - nginx
    home: /var/lib/nginx
    shell: /sbin/nologin
group:
  nginx:
    exists: true
    gid: 497
process:
  nginx:
    running: true
```

### 
`# goss validate`
```
...................

Total Duration: 0.040s
Count: 19, Failed: 0, Skipped: 0
```
