# Windows强迫症治愈指南
Windows越来越好用了，但对于强迫症患者来说还远远不够，冗长的右键菜单就是一个大问题。对于右键一级菜单，CCleaner或火绒就可以轻松解决，这里就不再赘述。现在的主要问题是右键的二级菜单，如新建菜单，发送到菜单。
## 删减右键-新建二级菜单
假如需要删除“新建 WinRAR 文件”菜单，Win+R 快捷键打开运行菜单，输入 regedit 打开注册表，定位到
```
计算机\HKEY_CLASSES_ROOT\.rar
```
将下面的 ShellNew 项重命名，如 ShellNew.bk，之后“新建 WinRAR 文件”菜单就在新建菜单里消失了，其他类似。终于舒服了……
## 删减右键-发送到菜单
此项不需要修改注册表，直接定位到以下目录
```
C:\Users\用户\AppData\Roaming\Microsoft\Windows\SendTo
```
这可以通过在文件资源管理器地址栏上输入 shell:sendto，或者 Win+R 快捷键打开运行菜单，输入 shell:sendto 实现。找到想要删除的项，将其属性设置为隐藏，即可删除相应的发送菜单项。又舒服了……
## 浏览器启动时打开页面
除了在浏览器内设置启动时打开的页面，还可以修改快捷方式属性。以Google chrome浏览器为例，当其快捷方式-属性-目标为以下内容时打开浏览器内设置的页面
```
"C:\Program Files (x86)\Google\Chrome\Application\chrome.exe"
```
当该值为以下内容时打开特定页面，如百度
```
"C:\Program Files (x86)\Google\Chrome\Application\chrome.exe" http:\\www.baidu.com
```
## 待续……
