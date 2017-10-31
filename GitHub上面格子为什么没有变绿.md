前段时间我的GitHub上面的格子只有我在new repository才会变绿，我就很纳闷，怎么这么不人性化，在我其他时间去上传自己一些项目的东西时候都没有任何颜色变化，我就上网查，终于找到了原因。

 修改方法很简单

 先查看自己git的账户名和邮箱

```
$ git config user.name
$ git config user.email
```
然后修改为和GitHub上面一直的账户名和邮箱

```
git config --global user.name "Your_username"
git config --global user.email "Your_email"
```
user.name后面有个**空格**，user.email后面也有**空格** 必须空格，不然不提示错误也不对

最后运行完没有任何提示后，你就可以在上传一个稍微改动的文件，刷新看看绿格，此时就有变化了。