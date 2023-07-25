# 项目部署
拉取项目到本地后，需要对源码进行修改：MySQL.h中，登录MySQL的信息，需要结合你本机的情况设定。 redis.cpp中redis::connect()函数中，登录redis的密码需要结合你本机的情况设定。

# 编译
使用CMakeLists.txt文件，在Linux上简单和可重复的方式来构建C++项目。
su root 
cd ./build
rm -rf *   # 删除上一次编译产生的build中的各种文件，上传的代码中由于文件大小关系，build文件中内容已被删除
cmake ..

本项目将上述操作写入了一个脚本文件autobuild.sh，编译过程简化为：
su root
./autobuild.sh

# 项目运行
前提需要先启动redis和nginx服务器，这里注意nginx和redis的配置文件修改。 最重要的是nginx配置文件中，配置负载均衡的ChatServer服务器集群中各个服务器的入口地址ip:port和负载均衡算法中选择每台服务器的权重weight。
