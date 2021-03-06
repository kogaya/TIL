# パーミッションとは

windowsで言うところの権限

読み込みや書き込みの権限を割り当てる

# 確認方法

`ls -l` でファイル一覧と一緒にパーミッションを表示することができる

```
例
drwxr-xr-x 2 archie users  4096 Jul  5 21:03 Desktop
drwxr-xr-x 6 archie users  4096 Jul  5 17:37 Documents
drwxr-xr-x 2 archie users  4096 Jul  5 13:45 Downloads
-rw-rw-r-- 1 archie users  5120 Jun 27 08:28 customers.ods
-rw-r--r-- 1 archie users  3339 Jun 27 08:28 todo
-rwxr-xr-x 1 archie users  2048 Jul  6 12:56 myscript.sh
```

### 読み方

- 最初の文字（'d' or '-'）はファイルの属性
  - 'd'はディレクトリ
  - '-'はディレクトリ以外（ファイル）
  
- 次の３文字('rwx','rw-'など)は管理者の権限
  - １文字目が'r'のときは読み取りの権限がある、'-'のときは権限無し
  - ２文字目が'w'のときは書き込みの権限がある、'-'のときは権限無し 
  - ３文字目が'x'のときは実行の権限がある、'-'のときは権限無し、その他の文字のときもたまにある
  
- 次の３文字はファイルグループの権限

- 次の３文字は一般ユーザの権限
  
# 設定方法

`chmod who=permissions filename`

- who
  - u:所有者ユーザ
  - g:ファイルが所属するグループ
  - o:その他のユーザ（一般ユーザ）
  
- permissions

  確認の項目と同じくrwx形式で指定
  
- filename

  変更するファイルのパス
  
### 省略形

`chmod 000 filename`

３分類の権限を同時に設定できる

１桁目が所有者、２桁目がグループ、３桁目が一般ユーザ

数値は以下の重みを加算したもの

```
r = 4
w = 2
x = 1
```

全権限の場合は4+2+1=7で7になる

例 `chmod 644 sample.txt` → `-rw-r--r--`
