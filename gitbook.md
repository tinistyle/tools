gitbook安装：
1. 安装node.js
2. npm install gitbook-cli -g

gitbook使用：
1. gitbook init：初始化文件夹
2. gitbook serve：运行

## markdown语法：

### 插入图片
`![图片不显示时提示信息](图片网址)` 前面不加叹号就是[超链接](https://www.bilibili.com)（可以使用a标签）

例：![这是一张图片](https://hbimg.huabanimg.com/ba237434c71679d5c4cfe5688578a14ad8e76095265e7-TfULRk)

可以使用html标签限制宽高:`<img src="https://hbimg.huabanimg.com/ba237434c71679d5c4cfe5688578a14ad8e76095265e7-TfULRk" height="200">`
<img src="https://hbimg.huabanimg.com/ba237434c71679d5c4cfe5688578a14ad8e76095265e7-TfULRk" height="200">

### 插入视频
html方式：
```
<iframe width="600" height="100%" src="//player.bilibili.com/player.html?aid=26457728&bvid=BV1As411W7h3&cid=45474759&page=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"> </iframe>
```
<iframe width="600" height="100%" src="//player.bilibili.com/player.html?aid=26457728&bvid=BV1As411W7h3&cid=45474759&page=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"> </iframe>


### 代码块
```python
a=1
c=4
b = a+c
```
也可以使用tab键

### 引用
使用>符号设置引用
多个符号左边空的位置不一样
> 一个>

>> 两个>

>>> 三个>

>>>> 四个>



### 改文字颜色
使用html：
<font color="red">红色文字</font>


## 插件
1. 新建 book.json 文件
2. 编辑book.json
    ```json
    {
        "title": "编写gitbook电子书教程",  // 网页名
        "description": "gitbook电子书教程",  // 网页简介
        "author": "sphard",  // 作者
        "language": "zh-hans",  // 网页使用语言
        "root": ".",

        "plugins": [  // 插件，使用gitbook install时会安装
            "donate", //打赏插件
            "github-buttons@2.1.0",  //GitHub按钮
            "edit-link" // 编辑插件
        ],

        "pluginsConfig": {  // 插件配置信息
            "donate": {
                "wechat": "https://sphard.com/images/wechatpay.jpg",  //图片地址
                "alipay": "https://sphard.com/images/alipay.jpg",
                "title": "",
                "button": "打赏",
                "alipayText": "支付宝打赏",
                "wechatText": "微信打赏"
            },
            "github-buttons": {
                "repo": "darrenliuwei/gitbook",
                "types": [
                    "star"
                ],
                "size": "small"
            },
            "edit-link": {
                "base": "https://github.com/darrenliuwei/gitbook/edit/master",
                "label": "Edit This Page"
            }
        }
    }
    ```
3. 使用 gitbook install 安装


## 部署到GitHub
1. 安装git
2. git init
3. 新建一个仓库，绑定：`git remote add origin git@github.com:tinistyle/gitbook.git`
4. git add + commit
5. 提交到远程仓库：`git push -u origin master`
6. 新建一个gh-pages分支，用于HTTP访问，只保留_book中编译成功的文件，并提交分支


## 部署到自己的服务器
使用Nginx，将_book文件夹下的文件传到Nginx的一个server下