# Goss
Goss

- OS
  - Amazon Linux

### インストール
`# curl -fsSL https://goss.rocks/install | sh`

- インストール完了と実行できるかの確認

`# goss --version`
```
-bash: goss: コマンドが見つかりません
```

- コマンドが見つからない場合の対処
$ sudo visudo
```
Defaults    secure_path = /sbin:/bin:/usr/sbin:/usr/bin
↓
Defaults    secure_path = /sbin:/bin:/usr/sbin:/usr/bin:/usr/local/bin
```

### テストを作成する
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

### 実行する
`# goss validate`
```
...................

Total Duration: 0.040s
Count: 19, Failed: 0, Skipped: 0
```
