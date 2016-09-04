# githook 自动部署

### 服务器

```
cd /home/USER
mkdir repos www
cd repos
// 建立裸库
git init --bare BRIDGE_REPO.git

cd /home/USER/www
git init
git remote add origin ~/repos/BRIDGE_REPO.git

cd /home/USER/repos/BRIDGE_REPO.git/hooks
vi post-receive
```

修改 post-receive 文件内容如下
```
#!/bin/sh

unset GIT_DIR

NowPath=`pwd`
DeployPath="../../www"

cd $DeployPath
git pull origin master

cd app
pm2 kill
npm install
pm2 start bin/www

cd $NowPath
exit 0
```

```
// 添加执行权限
sudo chmod +x post-receive
```

### 本地
```
git clone git@github.com:glassysky/home-page.git
cd home-page
git remote add deploy ubuntu@IP:/home/ubuntu/repos/BRIDGE_REPO.git
git add .
git commit -m "XXX"
git push deploy master
```
