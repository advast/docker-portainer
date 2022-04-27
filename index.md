## Docker安装
安装命令二选一即可   
CentOS / Debian / Ubuntu 一键安装 Docker 的命令是一样的，都 Docker 官方提供：
```
curl -fsSL https://get.docker.com -o get-docker.sh
sh get-docker.sh
```
Ubuntu 大陆地区的daocloud一键安装命令 安装docker：
```
sudo curl -sSL https://get.daocloud.io/docker | sh
```
   
启动docker：
```
systemctl start docker
```
查看docker服务状态：
```
systemctl status docker
```
设置docker开机自启：
```
systemctl enable docker
```
   
## Portainer安装   
首先在/root 文件夹内新建目录/portainer   
然后拉取映像：   
```
docker pull portainer/portainer
```
创建并部署portainer：
```
docker run -d -p 9000:9000 --name portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce:2.11.1
```
Portainer更新命令和官网说明文档地址：  
停止和删除portainer：   
```
docker stop portainer
```
```
docker rm portainer
```
拉取新版本映象（以社区版 ce2.11.1版本为例）：   
```
docker pull portainer/portainer-ce:2.11.1
```
部署新版本：   
```
docker run -d -p 8000:8000 -p 9000:9000 -p 9443:9443 --name=portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce:2.11.1
```
官网说明文档地址：   
https://docs.portainer.io/v/ce-2.11/start/upgrade/docker
