## Git 上传文件到Github

1. 创建本地库：在合适的位置创建文件夹，进入该目录下，且上传的文件要在改文件夹下，然后将该文件夹变成git可以管理的仓库：

    ``` git init
    git init
    ```
2. 进在Github端创建仓库，然后将远程仓库与本地仓库相互关联:

    ``` 
     git remote add origin git@github.com:Stylite-Y/installation-tutorial 	// com后面根据自己的github名字和库名更改
    ```

3. 然后先将文件添加到版本库，再用命令`git commit`告诉Git，把文件提交到仓库

    ``` 
    git add Pytorch-install.md
    git commit -m "this is the ML algotithm platform install tutorial"
    ```

4. 之后将文件上传到github仓库

    ``` 
    git push -u origin master //由于远程库是空的，我们第一次推送master分支时，加上了-u参数，Git不但会把本地的master分支内容推送的远程新的master分支，还会把本地的master分支和远程的master分支关联起来，在以后的推送或者拉取便不需要了
    ```

    

## Git中遇到的问题

1. 第一次 git push 时遇 permission denied 时（如下图)

    ![git_1](https://raw.githubusercontent.com/Stylite-Y/MyTypora/master/img/git_1.PNG)

    解决方案：

    （1）在用户主目录下，看看有没有.ssh目录，如果有，再看看这个目录下有没有id_rsa和id_rsa.pub这两个文件，如果已经有了，可直接跳到下一步。如果没有，打开Shell（Windows下打开Git Bash），创建SSH Key：

    ```
     ssh-keygen -t rsa -C "yn_hy14753@163.com"
    ```

    ![ssh_computer](https://raw.githubusercontent.com/Stylite-Y/MyTypora/master/img/ssh_computer.PNG)

    可以在用户主目录里找到.ssh目录，里面有id_rsa和id_rsa.pub两个文件，这两个就是SSH Key的秘钥对，id_rsa是私钥，不能泄露出去，id_rsa.pub是公钥，可以放心地告诉任何人。

    （2）登录github，创建ssh key，并将id_rsa.pub中的内容复制到github中

    ![ssh-git](https://raw.githubusercontent.com/Stylite-Y/MyTypora/master/img/ssh-git.png)

    （3）然后通过运行以下代码把git仓库和这个SSH key 关联上

    ​	

    ```
    ssh-agent bash
    ssh-add "D:\Program\emacs-26.3-x86_64\.ssh"
    ```

    

2. 若git push 过程遇到！[rejected]的问题，如下图

    ![rejected](https://raw.githubusercontent.com/Stylite-Y/MyTypora/master/img/rejected.PNG)

    解决方法：是因为在线上生成、编辑了README.md文件，而本地代码文件中不包含它，所以线上线下就对不上了。

    只需要进行线上和线下代码进行合并即可：

    ```
     git pull --rebase origin master
    ```

    

    

    

