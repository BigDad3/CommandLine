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


---

设置两个git账号：

>cd /Users/{accountname}/.ssh

生成ssh key
>ssh-keygen -t rsa -C "xxx@xx.com"

回车之后提示你生成的ssh key 的存储路径和名称，可以自己指定路径和名称
>Generating public/private rsa key pair.
>Enter file in which to save the key (/Users/{username}/.ssh/id_rsa):

拷贝生成的公钥
>pbcopy < ~/.ssh/id_rsa_work.pub

执行ssh-agent让ssh识别新的私钥
>ssh-add ~/.ssh/id_rsa_work

创建配置文件
>touch config

配置文件内容
>\#work Git
>
>Host workgit 
>
>HostName IP Address #域名也可
>
>User think
>
>IdentityFile ~/.ssh/id_rsa_work

>\#myself Git
>
>Host myselfgit
>
>HostName IP Address #域名也可
>
>User think
>
>IdentityFile ~/.ssh/id_rsa_myself
