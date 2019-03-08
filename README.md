#基于nginx实现科学上网的负载均衡
只有稳定的科学上网，才能更好的学习编程技术。

###结果
- 理论上提高多线程下载的时候。但是瓶颈在于直接面向客户端的vps。
- 从流量上看，你的请求直接是发送到了国内的vps中，这个几乎不可能被ban。
- 国外vps也避免了被封的风险，即使被封了，也可以修改nginx的配置，这样就不需要动客户端了
- 因为国内vps所在的机房的关系，可能与国外vps延迟甚小。所以这种情况下会大大提高速度。
- 其他的自己去想吧，我也只是突发奇想。
### 思路
国内的vps安装nginx，然后将请求转发到国外vps上。


### 前提准备
- 1台以上数量的vps（可以访问国外网站的），如搬瓦工，linode等；
- 1台带宽够大的国内vps；

# 具体实现
## 安装shadowsocks
在国外vps上安装shadowsocks，参考[https://github.com/dengjunwen/ss-fly](https://github.com/dengjunwen/ss-fly)
## 安装nginx
- 直接使用yum install nginx
- 安装好nginx后，配置/etc/nginx/nginx.conf文件（贴出部分代码片段）：

## 本地安装小飞机