安装配置使用

依赖

```shell
yum install curl policycoreutils-python openssh-server postfix -y
systemctl start postfix
systemctl enable postfix
```

安装

```shell
rpm -ivh gitlab-ce-10.2.2-ce.0.el7.x86_64.rpm  # rpm安装
vim /etc/gitlab/gitlab.rb  # 修改配置文件
	external_url 'http://ip地址'  # 设置访问的地址
gitlab-ctl reconfigure  # 重新配置

gitlab-ctl status  # 启动
gitlab-ctl restart  # 重启
```

使用

1. 打开设置的ip（或主机的ip）
2. 设置密码
3. 登陆（默认用户root）

#### 系统设置

登录页设置

+ 关闭注册：
  1. 登陆系统，
  2. 打开设置区
  3. 最后的设置
  4. 关闭sign up
+ 外观设置：
  1. 前两步同关闭注册
  2. 找到外观设置
  3. 添加标题、说明、logo和导航栏等

#### 仓库管理

1. 创建组
   1. 路径