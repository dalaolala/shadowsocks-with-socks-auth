Shadowsocks with socks5 auth
===========

Based on [shadowsocks release 2.8.2](https://github.com/shadowsocks/shadowsocks/releases/tag/2.8.2)

Socks5 auth added by [@ihciah](https://github.com/ihciah)

With this version of shadowsocks, you can run `sslocal` in public network. You can specify a username and a password of your socks5 server.

But please pay attention, the username and password will be transmitted in plaintext. However, if you don't care, you can use it without worrying about web scanning.

For example, running a `ss-local` on VPS in China connecting to outside, then you can set the socks proxy in some software like `Telegram` to avoid running a shadowsocks client on mobile phones.    

For usage please run `local.py`.

yum install python-setuptools && easy_install pip

yum install git

git clone -b  master https://github.com/dalaolala/sssocket5.git

cd sssocket5

python setup.py install

sslocal -s 服务器 -p 端口 -b "0.0.0.0" -l 1080 -k 密码 --socks-user socks5用户名 --socks-pass socks5密码 -m 加密方式

后台运行

nohup sslocal -s 服务器 -p 端口 -b "0.0.0.0" -l 1080 -k 密码 --socks-user socks5用户名 --socks-pass socks5密码 -m 加密方式 >/dev/null 2>&1 &
