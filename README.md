# GANppt

（1）台湾大学李宏毅的GAN网络PPT以及部分源代码

（2）当传输的文件超过25mb时，在github中直接拖拽是不可以进行的
其中新电脑要配置github中的SSH Key 
   在git Bash中进行重新的配置  https://blog.csdn.net/ziziju/article/details/117914569  （具体的实现步骤）
   
   2.1 ssh -T git@github.com  ##测试SSH密钥是否配置成功


（3）上传大于25MB文件的关键步骤：在传输界面进入 git Bash中     ##知乎完整https://zhuanlan.zhihu.com/p/374650864
 git config --global --add safe.directory '%%%当前文件路径'
 git branch -m master main   ##进入main分支环境中去  git分支从master 中转换到main 分支中
#创建本地仓库环境
git init 
 
#安装大文件上传应用git lfs
git lfs install 
 
#追踪要上传的大文件，*表示路径下的所有文件
git lfs track *
 
#添加先上传的属性文件(要先上传属性文件，不然git commit -m "pre”#添加属性文件上传的说明
git add .gitattributes 
 
#建立git push origin master  
git remote add origin git@github.com:zhangbeibei00/git_test.git  #上传属性文件具体的库的密钥 具体查询
 
#添加要上传的大文件，*表示路径下的所有文件git commit -m "Git LFS commit"#添加大文件上传的说明
git add *
 
#先进行初步的第一轮提交
 git commit -m "add gan_v10.pptx"

#上传大文件
git push origin master   

(4)#如有提交问题合并冲突问题参见博客
https://www.cnblogs.com/liangmu66/articles/13479802.html

#正确的解决方法就是将你的仓库和你的gitee合并了，用填充的方法，即：
git pull --rebase origin master  ##git pull --rebase origin main

#输入上述命令，其中origin代表你的仓库uri，后面的master表示将当前的提交到本地仓库的内容和远程仓库合并；
再输入如下命令，即可将本地仓库推送到远程仓库：
git push origin master

