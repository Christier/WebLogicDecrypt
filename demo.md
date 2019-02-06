# 获取本地的weblogic用户名、密码

C:\hibunexc\weblogic\user_projects\domains\base_domain\security\tmp> `call C:\hibunexc\weblogic\wlserver\server\bin\setWLSEnv.cmd`<br>

>Your environment has been set.                                                                   

C:\hibunexc\weblogic\user_projects\domains\base_domain\security\tmp> `C:\pleiades\java\8\bin\javac.exe Decrypt.java`<br>

C:\hibunexc\weblogic\user_projects\domains\base_domain\security\tmp> `java -cp .;%CLASSPATH% Decrypt {AES}e5xAUmNTMMpwGmDPYP1iqS9W+naA7wf2G5UTMHjS8dI=`<br>

>Decrypted Password is:ba888888`

C:\hibunexc\weblogic\user_projects\domains\base_domain\security\tmp> `java -cp .;%CLASSPATH% Decrypt {AES}8iHTZD93aAKShp7NgX0vtVfe0zhYXXC/k3JTZkA3UZA=`<br>

>Decrypted Password is:weblogic`
