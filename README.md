# maven-repo
My personal github maven repository.

## Usage
maven deploy:
```
  <distributionManagement>
    <repository>
      <id>zxc-mvn-repo</id>
      <url>file:/home/zxc/code/maven-repo/repository/</url>
    </repository>
  </distributionManagement>
```

git push:
```
cd /home/zxc/code/maven-repo/
git init
git add repository/*
git commit -m 'deploy xxx'
git remote add origin git@github.com:Lawrence-zxc/maven-repo.git
git push origin master
```

pom.xml:
```xml
    <repositories>
        <repository>
            <id>zxc-maven-repo</id>
            <url>https://raw.githubusercontent.com/zxc/maven-repo/master/repository</url>
        </repository>
    </repositories>
```

#在github上搭建个人maven仓库
主要分三步：

* deploy到本地目录
* 把本地目录提交到gtihub上
* 配置github地址为仓库地址

##配置local file maven仓库
deploy到本地,maven可以通过http, ftp, ssh等deploy到远程服务器，也可以deploy到本地文件系统里.

##github maven仓库的使用
github使用了raw.githubusercontent.com这个域名用于raw文件下载。所以使用这个maven仓库，只要在pom.xml做上面的类型添加repository即可.
命令如下(个人喜欢使用命令行来deploy,避免在项目里显式配置):
```
mvn deploy -DaltDeploymentRepository=zxc-mvn-repo::default::file:/home/zxc/code/maven-repo/repository/
```

##其他方式
`site-maven-plugin`
