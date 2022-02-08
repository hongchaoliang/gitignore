# gitignore
Java .gitignore

本地创建了一个project
并在码云上创建了一个仓库，想要将本地的仓库链接到远程仓库
我用的是如下方法：
git init    初始化本地仓库
git remote add origin XXX     添加远程仓库地址
如果你在这之后就执行
git add -A，
git commit -m " "
git push origin master,那么就会出现这个问题(被拒绝)，所以在remote add后不要着急git add，一定要git pull origin master，出现这个原因
是因为你在码云创建的仓库有ReadMe文件，而本地没有，造成本地和远程的不同步，
那么有两种方案可以解决：
one ：
本地没有ReadMe文件，那么就在本地生成一个：
git pull --rebase origin master     本地生成ReadMe文件
git push origin master
two：
那我就强制上传覆盖远程文件，
git push -f origin master
(这个命令在团队开发的时候最好不要用,否则可能会有生命危险)
