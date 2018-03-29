# Tomcat源码学习（1）
## *IntelliJ IDEA 17.3.3* 导入 *Tomcat 9.0.6*源码

1. 下载源码 [*tomcat_9.0.6*](http://mirrors.hust.edu.cn/apache/tomcat/tomcat-9/v9.0.6/src/apache-tomcat-9.0.6-src.tar.gz)
2. 启动 *IDEA*. 点击 *Open*,选择刚才下载的文件解压后的路径。
3. 打开后，在项目上右击鼠标，选择*Add Framework Support* , 然后点击 *maven* .
4. 设置*maven* __pom__ 文件。
5. 根据本机jdk版本设置 __pom__ 中的版本

        <build>
            <plugins>
                <plugin>
                    <artifactId>maven-compiler-plugin</artifactId>
                    <configuration>
                        <source>1.8</source>
                        <target>1.8</target>
                    </configuration>
                </plugin>
            </plugins>
        </build>

6. 如果设置为 __9__ 版，会报错
        
        程序包 javax.xml.soap 不可见 (程序包 javax.xml.soap 已在模块 java.xml.ws 中声明, 但该模块不在模块图中)

7. 调用 *maven* __install__命令，解决依赖。

至此已导入完毕

---
## 调试
1. Run/Debug Configuration
2. 点击左上角 __+__ 加号，选择 *Application* 
3. __Main class__ 设置为 *org.apache.catalina.startup.Bootstrap*
4. 点击 __OK__
