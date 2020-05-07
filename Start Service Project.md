#### 在IntelliJ IDEA启动一个service项目

**背景**：在前端开发过程中，通常连线上环境进行开发。但是线上环境总是出现问题，就会阻碍前端开发的进度。从而我们需要在本地启动service项目，从而不受线上环境的影响。

**jdk**：Intellij 自带jdk版本为13.0.1，但是项目运行所需要的jdk版本为1.8,需要到官网下载相应的版本jdk-8u251-macosx-x64.dmg，然后进行安装。
在File -> Project Structure -> Project -> Project SDK中替换jdk版本。

jdk高版本为何不适用？

**maven配置**：在maven官网上下载 apache-maven-3.6.3-bin.tar.gz，然后解压，将apache-maven-3.6.3文件夹放在Library目录下。打开terminal,设置maven环境变量。
``` 
 $ vi ~/.bash_profile
 添加以下两行代码，之后保存并退出vi
 export M3_HOME=/Library/apache-maven-3.6.3
 export PATH=$M3_HOME/bin:$PATH
 输入命令以使bash_profile生效
 $ source ~/.bash_profile
 输入mvn -v查看Maven是否安装成功
 ```

**依赖包引入**
在右侧工具栏Maven中，点击Download Sources。  
下载完成后，右击pom.xml -> Maven -> Reimport

**Build 和 Run**
右击最外侧文件夹，点击build。   
build完成后，选择application.java，点击Run。
