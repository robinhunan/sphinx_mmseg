mmseg 安装(中文分词)
下载mmseg源码包
#cd mmseg-3.2.14
#./bootstrap
#./configure --prefix=/usr/local/mmseg3
# make 
# make install

sphinx 安装
在sphinx源码目录执行
# sh buildconf.sh 
./configure --prefix=/usr/local/sphinx  --with-mmseg  -with-mmseg-includes=/usr/local/mmseg3/include/mmseg  -with-mmseg-libs=/usr/local/mmseg3/lib/  --with-mysql --enable-id64
make && make install

启动
#/usr/local/sphinx/bin/indexer --config /usr/local/sphinx/etc/sphinx.conf --all #创建索引
#/usr/local/sphinx/bin/searchd --config /usr/local/sphinx/etc/sphinx.conf #启动索引服务
#/usr/local/sphinx/bin/indexer --config /usr/local/sphinx/etc/sphinx.conf --rotate --all #重建增量索引
