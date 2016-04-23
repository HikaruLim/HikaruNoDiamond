> problem

* in win10
* git error:
      fatal:unable to access 'https://.../':error ... 
      CAfile: D:/Git/mingw64/ssl/certs/ca-bundle.crt
      CApath: none ```
***i have no idea about "D:/Git/..." yet***
***我还不知道这个路径到底是怎么来的***

Alim 2016.04.23
---

> Chinese ver:

1、
找到配置文件：C:\ProgramData\Git\config
打开后看到：``` sslCAInfo = D:/Git/mingw64/ssl/certs/ca-bundle.crt ```

但是按这个路径去找这个ca-bundle.crt文件却找不到，
所以，在本地搜索真正有用的路径。找到一个。于是修改上边提到的
sslCAInfo。
==>
 ``` sslCAInfo = C:/Users/.../AppData/Local/GitHub/PortableGit_.../usr/ssl/certs/ca-bundle.crt ```

2、
然后在bash上进行。
``` config -l ```
找到sslCAInfo信息，也就是 ```D:/Git/mingw64/ssl/certs/ca-bundle.crt ```
然后
``` git config --system http.sslcainfo C:/Users/.../AppData/Local/GitHub/PortableGit_.../usr/ssl/certs/ca-bundle.crt ```

**done!**

---

> English ver:

1、
find config file: C:\ProgramData\Git\config
open it and you can see:``` sslCAInfo = D:/Git/mingw64/ssl/certs/ca-bundle.crt ```

when go to find ca-bundle.crt with this path,found nothing.
so i search a real path which involes a file ca-bundle.crt in local,
and i found it.
then modify sslCAInfo with it in the config file.
==>
 ``` sslCAInfo = C:/Users/.../AppData/Local/GitHub/PortableGit_.../usr/ssl/certs/ca-bundle.crt ```

 2、
 then work in git bash.
``` git config -l ```

you will see sslCAInfo, ```D:/Git/mingw64/ssl/certs/ca-bundle.crt ```

then
``` git config --system http.sslcainfo C:/Users/.../AppData/Local/GitHub/PortableGit_.../usr/ssl/certs/ca-bundle.crt ```

**done!**