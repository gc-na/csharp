# [操作系统] C Shell (csh) ftp 使用方法: 传输文件

## 概述
`ftp` 命令用于在计算机之间通过网络传输文件。它允许用户连接到远程主机，并进行文件的上传和下载操作。

## 用法
基本语法如下：
```
ftp [选项] [参数]
```

## 常用选项
- `-i`：关闭交互模式，适合批量传输文件。
- `-v`：启用详细模式，显示传输过程中的详细信息。
- `-n`：禁止自动登录，适用于需要手动输入用户名和密码的情况。

## 常见示例
1. 连接到远程 FTP 服务器：
   ```bash
   ftp ftp.example.com
   ```

2. 使用用户名和密码登录：
   ```bash
   ftp -n ftp.example.com
   user username password
   ```

3. 下载文件：
   ```bash
   get filename.txt
   ```

4. 上传文件：
   ```bash
   put filename.txt
   ```

5. 下载整个目录：
   ```bash
   mget *
   ```

## 提示
- 在使用 `ftp` 进行文件传输时，确保网络连接稳定，以避免传输中断。
- 使用 `-i` 选项可以提高传输效率，特别是在处理多个文件时。
- 定期检查 FTP 服务器的连接状态，以确保能够顺利进行文件传输。