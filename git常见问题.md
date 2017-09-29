**使用git遇见的问题**
--
在我使用的过程中发现一些问题，并且以自己的方式解决，记录一下

**问题一**

```
$ git add readme.txt
fatal: pathspec 'readme.txt' did not match any files
```
**原因**：出现这个就是说当前的目录没有与之匹配的文件，也就是路径不对，你要找的文件不在当前路径

**解决办法**：

```
$ cd
$ pwd
$ cd 文件名（文件夹名）
$ pwd
 .....
```
意思就是先看当前目录在哪儿，看是否是在你要添加的文件的那个目录下，如果不是就要切换到相应目录，如果你认为你已经切换到了正确的路径，但是还是报错，那就关掉git，从头再来（不要问我为什么，反正在有的时候还挺管用的），当然也可以用相对路径。

**问题二 **

![问题一](http://img.blog.csdn.net/20170928081448638?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvZXJkYWlkYWk=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

**原因**：在commit的时，没有`-m "描述"`，没有添加描述，跳到一个提示窗口

**解决办法**：输入 `:wq` 返回，不管提示窗口上的光标在哪儿，直接输入就好。也可以下次commit的时候，记住添加变更描述。