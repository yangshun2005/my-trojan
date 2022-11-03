alls:



gettjc:
	curl https://dlcas.oss-cn-beijing.aliyuncs.com/softwarepackage/vpn/trojan/trojan-1.16.0-linux-amd64.tar.xz -o trojan-1.16.0-linux-amd64.tar.xz
	xz -d trojan-1.16.0-linux-amd64.tar.xz  && tar xf trojan-1.16.0-linux-amd64.tar 
	cd trojan
	## get cli-config-linux.json from oss
	trojan -c cli-config-linux.json

getpc4: gettjc
	git clone https://github.com/rofl0r/proxychains-ng   #https://gitee.com/ligangcould/proxychains-ng
	cd proxychains-ng
	./configure
	sudo make && make install
	sed -i s/socks4\ \ \ \ 127\.0\.0\.1\ 9050/\#socks4\ \ \ \ 127\.0\.0\.1\ 9050/g  /etc/proxychains.conf
	echo 'socks5  127.0.0.1 1081'  >> /etc/proxychains.conf
	proxychains4 curl cip.cc

	