#命令行创建GitHub仓库

用如下命令可以直接在终端创建GitHub仓库：

>curl -u 'username' https://api.github.com/user/repos -d '{"name":"RepoName"}'

其中，username是你的用户名，RepoName是你想命名的仓库名。这条命令执行后输入密码就创建成功了，会有仓库相关信息的回显。

创建成功之后就可以做其他操作了：

>echo "# CommandLine" >> README.md
>
>git init
>
>git add README.md
>
>git commit -m "first commit"
>
>git remote add origin https://github.com/username/
RepoName.git
>
>git push -u origin master
