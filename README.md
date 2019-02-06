# WebLogicDecrypt

1.获取服务器上的Weblogic用户名、密码 
---

  工具：Xshell
   
 1. 连接至服务器上,新建目录  mkdir /scripts/DecryptionDemo<br>  
 2. 将Decrypt.java放到新建的目录中.Decrypt.java就是具体用户解密的代码<br>  
 3. 寻找当前服务器上的weblogic的**wljarbuilder.jar**<br> 
 

>locate wljarbuilder.jar
>进入该路径，生成wlfullclient.jar，指令为： 
```Bash
java –jar wljarbuilder.jar
``` 
>将生成的wlfullclient.jar复制到/scripts/DecryptionDemo目录下：
```Bash
cp xxx/wlserver/server/lib/wlfullclient.jar /scripts/DecryptionDemo
```

 4. 寻找当前服务器上的weblogic的**cryptoj.jar**.并复制到/scripts/DecryptionDemo目录下.<br>  
 5. 寻找当前服务器上的weblogic的**SerializedSystemIni.dat**,并复制到/scripts/DecryptionDemo目录下.<br>  
 6. 在/scripts/DecryptionDemo路径下,编译Decrypt.java.  javac -cp "$CLASSPATH:/scripts/DecryptionDemo/*" Decrypt.java<br>  
 7. 寻找账号密码文件boot.properties，获取原服务器上存储的加密后的用户名、密码.<br>  
 8. 在/scripts/DecryptionDemo路径下，执行解密操作：<br>  
```Bash
java -cp "$CLASSPATH:/scripts/DecryptionDemo/*" Decrypt username
java -cp "$CLASSPATH:/scripts/DecryptionDemo/*" Decrypt password
``` 

___
2.获取本地的weblogic用户名、密码
---

　　1. 创建一个单独的目录, 例如 C:\DecryptionDemo <br>  
　　2. 创建一个Java文件Decrypt.java, 代码内容同“1”中相同.<br>  
　　3. 运行相关命令解密位于`D:\bea\user_projects\domains\1034\servers\AdminServer\security\boot.properties`文件中的字符串.<br>  
  ```Bash
  call C:\weblogic\wlserver\server\bin\setWLSEnv.cmd
  copy C:\xx\weblogic\user_projects\domains\base_domain\security\SerializedSystemIni.dat .\
  javac Decrypt.java
  java -cp .;%CLASSPATH% Decrypt {AES}e5xAUmNTMMpwGmDPYP1iqS9W+naA7wf2G5UTMHjS8dI=
  ```
>ba888888<br>  
>weblogic每个数据域的加密方式是不同的，也就是说每个数据域下的加密文件只适用于当前数据域。
