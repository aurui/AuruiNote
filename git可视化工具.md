# git可视化工具

注意：所有可视化工具都是在安装了git的前提下，如果没有安装，请到[Git 官网](https://git-scm.com)下载
## 一、SourceTree
请参考之前的Git 环境搭建、安装及 SourceTree 使用手册

## 二、TortoiseGit
### 1.下载与安装

请到[TortoiseGit](https://tortoisegit.org/download/)下载，根据提示点击下一步即可安装，默认语言是English，不过TortoiseGit还提供了各种语言的语言包，像我一样英语不好的可以安装一下

### 2.设置
一般TortoiseGit安装好就可以了，如果不行就需要设置下git的凭证
右键选择TortoiseGit选择设置，设置下git的凭证，也可以设置下右键菜单

### 3.基本操作
我是用了语言包的，操作起来方便易懂，就以这个来介绍了
#### 1.创建版本库（相当于: git init）
    新建一个空文件夹，右键操作
![image](https://raw.githubusercontent.com/aurui/AuruiNote/master/images/01.png)
![image](https://github.com/aurui/AuruiNote/blob/master/images/%E6%96%B0%E5%BB%BA%E7%89%88%E6%9C%AC%E5%BA%93.png?raw=true)
    
#### 2.克隆版本库 (相当于：git clone https://github.com/aurui/AuruiNote.git )
![image](https://github.com/aurui/AuruiNote/blob/master/images/%E5%85%8B%E9%9A%86%E7%89%88%E6%9C%AC%E5%BA%93.png?raw=true)
![image](https://github.com/aurui/AuruiNote/blob/master/images/%E5%85%8B%E9%9A%86%E9%A1%B9%E7%9B%AE.png?raw=true)
    
#### 3.提交 (相当于：git commit)
![image](https://github.com/aurui/AuruiNote/blob/master/images/%E6%8F%90%E4%BA%A4.png?raw=true)
![image](https://github.com/aurui/AuruiNote/blob/master/images/%E6%8F%90%E4%BA%A4%E5%90%8E%E7%9A%84%E7%8A%B6%E6%80%81.png?raw=true)

#### 4.查看更新日志 (相当于： git log)
![image](https://github.com/aurui/AuruiNote/blob/master/images/%E6%8F%90%E4%BA%A4%E6%97%A5%E5%BF%97.png?raw=true)

#### 5.推送到远程 (相当于：git push origin master)
![image](https://github.com/aurui/AuruiNote/blob/master/images/%E6%8E%A8%E9%80%81%E5%88%B0%E8%BF%9C%E7%A8%8B%20(1).png?raw=true)
![image](https://github.com/aurui/AuruiNote/blob/master/images/%E6%8E%A8%E9%80%81%E5%88%B0%E8%BF%9C%E7%A8%8B%20(2).png?raw=true)
    
#### 6.新建分支 (相当于： git branch dev)
![image](https://github.com/aurui/AuruiNote/blob/master/images/%E6%96%B0%E5%BB%BA%E5%88%86%E6%94%AF.png?raw=true)
    
#### 7.切换分支 （相当于：git checkout dev）
![image](https://github.com/aurui/AuruiNote/blob/master/images/%E5%88%87%E6%8D%A2%E5%88%86%E6%94%AF.png?raw=true)
    
#### 8.合并分支 (相当于： git merge hotfix)
![image](https://github.com/aurui/AuruiNote/blob/master/images/%E5%90%88%E5%B9%B6%E5%88%86%E6%94%AF.png?raw=true)
    
![image](https://github.com/aurui/AuruiNote/blob/master/images/%E5%90%88%E5%B9%B6%E5%88%86%E6%94%AF%20(2).png?raw=true)

### 4.优点
#### 1.文件状态信息清晰可见
![image](https://github.com/aurui/AuruiNote/blob/master/images/%E6%96%87%E4%BB%B6%E7%8A%B6%E6%80%81.png?raw=true)
![image](https://github.com/aurui/AuruiNote/blob/master/images/%E5%9B%BE%E6%A0%87.png?raw=true)

#### 2.文件比较清晰明了
![image](https://github.com/aurui/AuruiNote/blob/master/images/%E5%86%B2%E7%AA%81.png?raw=true)

#### 3.分支图易理解
![image](https://github.com/aurui/AuruiNote/blob/master/images/%E5%88%86%E6%94%AF%E5%9B%BE%20(1).png?raw=true)

#### 4.安装学习都很简单，很容易上手

### 5.缺点
#### 1.没有管理主页面，操作都要点开资源管理器后再操作

#### 2.不能直观的看到当前分支和提交日志

#### 3.分支没有文件夹的概念，当分支多时难以选择
![image](https://github.com/aurui/AuruiNote/blob/master/images/%E5%88%86%E6%94%AF%E9%80%89%E6%8B%A9.png?raw=true)

### 总结：习惯用SVN的可以试一下，和SVN的操作基本类似，但是操作起来没有SourceTree方便
