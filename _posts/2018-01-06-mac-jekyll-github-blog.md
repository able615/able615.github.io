# Mac下使用Jekyll和github搭建个人博客
## 1、安装ruby
使用brew安装
``` python
$ brew install ruby
```
查看ruby版本
``` python
$ ruby -v
ruby 2.5.0p0 (2017-12-25 revision 61468) [x86_64-darwin17]
```
## 2、安装gem
Mac机器已经自带gem,没有gem的[参考网站](https://rubygems.org/pages/download)安装
``` python
$ gem -v
2.7.4
```
给gem更换国内的源，原始源由于“墙”的原因，很蛋疼
``` python
# 查看原始源列表
$ gem sources -l
https://rubygems.org/

#将源移除
$ gem sources --remove https://rubygems.org/

#添加国内源
$ gem sources --add http://gems.ruby-china.org/

#缓存源
$ gem sources -u

#再次查看源列表，确认源已更新
$ gem sources -l
http://gems.ruby-china.org/
````
注意：这里使用http://gems.ruby-china.org ，而不是 https://gems.ruby-china.org ，是因为可能有SSL证书问题

## 3、安装jekyll
``` python
$ sudo gem install jekyll
```

## 4、安装博客
安装以下组件
``` python
1 $ sudo gem install bundler
2 $ sudo gem install jekyll-paginate
3 $ sudo gem install jekyll-gist
```
创建博客(如果没有找到jekyll命令，重启下终端)
``` python
$ sudo jekyll new able615blog
```
安装过程会显示一堆安装内容，关注最后一行
``` python
New jekyll site installed in /Users/liuyw/able615blog.
```

## 5、本地启动博客
进入到安装目录执行命令
```python
$ cd /Users/liuyw/able615blog
$ sudo jekyll serve
```
输出
``` python
Password:
Configuration file: /Users/liuyw/able615blog/_config.yml
            Source: /Users/liuyw/able615blog
       Destination: /Users/liuyw/able615blog/_site
 Incremental build: disabled. Enable with --incremental
      Generating... 
                    done in 0.415 seconds.
 Auto-regeneration: enabled for '/Users/liuyw/able615blog'
    Server address: http://127.0.0.1:4000/
  Server running... press ctrl-c to stop.
```
将http://127.0.0.1:4000/复制到浏览器，能打开就表示正常了。
![images](https://note.youdao.com/yws/api/personal/file/WEBc247825c117d65c808f28b3beb342ca3?method=getImage&version=1561&cstk=e7Z-UHIH)

## 6、部署到github
按照自己的github账号创建一个仓库,固定格式username.github.io，这个代码仓库就是博客源码存放地，博客公网链接就是：https://able615.github.io
``` python
https://github.com/able615/able615.github.io.git
```
将本地内容和github上的仓库关联
``` python
1 $ cd /Users/liuyw/able615blog
2 $ sudo git init
3 $ sudo git add .
4 $ sudo git commit -m "first commit"
5 $ sudo git remote add origin https://github.com/able615/able615.github.io.git
6 $ sudo git push -u origin master
```
这里注意替换为你自己的地址，在执行git push的时候，需要输入github的账号和密码。 
完成后在浏览器上输入: able615.github.io，就可以看见博客了。


