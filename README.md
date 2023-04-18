一、开发环境搭建

1. 设置镜像地址

vim ~/.bashrc
export REPO_URL='https://mirrors.tuna.tsinghua.edu.cn/git/git-repo/'
source ~/.bashrc

2、安装repo

snap install git-repo
curl https://storage.googleapis.com/git-repo-downloads/repo-1 > /snap/bin/repo
chmod a+x /snap/bin/repo

3.  软链python3

cd /usr/bin/
ls python* -all #查看python软链
ln -s python3 python

二、克隆编译

repo init -u https://github.com/lynx-liu/qemuEnv.git -b main
repo sync
cd external
git clone https://github.com/qemu/qemu.git -b master
cd qemu
./android/rebuild.sh -notests --sdk_build_number=202304182130
