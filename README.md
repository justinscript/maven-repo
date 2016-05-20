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

pom.xml:
```xml
    <repositories>
        <repository>
            <id>zxc-maven-repo</id>
            <url>https://raw.githubusercontent.com/zxc/maven-repo/master/repository</url>
        </repository>
    </repositories>
```

git todo:
```
cd /home/zxc/code/maven-repo/
git init
git add repository/*
git commit -m 'deploy xxx'
git remote add origin git@github.com:Lawrence-zxc/maven-repo.git
git push origin master
```


#在github上搭建个人maven仓库
主要分三步：

* deploy到本地目录
* 把本地目录提交到gtihub上
* 配置github地址为仓库地址
