
## 这什么？

这是 FEX 团队对外 Blog 的源码，将文章提交到这里后就会在 <http://fex.baidu.com> 上展现。

## 如何写？


### 环境搭建



这个 Blog 系统是基于 [jekyll](http://jekyllrb.com/) 搭建的，为了方便本地编辑和看效果，需要讲本项目 clone 至本地环境，并在本机安装 jekyll 环境。

#### Mac用户

请使用如下命令（其中 gem 是 [Ruby](https://www.ruby-lang.org/)  的包管理工具）完成 jekyll 的安装：

    gem install jekyll

#### Windows 用户

jekyll 官方对 winodws 的支持程度很低，但有高手解决了这个问题：[Building portable Jekyll for Windows](http://www.madhur.co.in/blog/2013/07/20/buildportablejekyll.html)，并给出了一个解压即可运行的版本，下载地址： [PortableJekyll 1.3.0[百度网盘]](http://pan.baidu.com/s/1dDqtzUT)

解压文件并配置环境变量，即可完成 jekyll 的安装。

下边以 jekyll 的解压目录为 e:\jekyll 介绍环境变量的配置：

1. 给环境变量中新建变量：

	JEKYLL_HOME 取值为 e:\jekyll

2. 给 path 变量增加
	%JEKYLL_HOME%\ruby\bin;%JEKYLL_HOME%\devkit\bin;%JEKYLL_HOME%\git\bin;%JEKYLL_HOME%\Python\App;%JEKYLL_HOME%\devkit\mingw\bin;%JEKYLL_HOME%\curl\bin

完成 jekyll 配置后，通过如下命令检查是否配置成功：
	
	jekyll -h 

#### 在本地启动 blog
	
完成 jekyll 的安装后，在blog源码目录，通过如下命令就能在本地查看效果了:

    jekyll serve --watch	

### 新建草稿

新文章编写时请先浏览 `_drafts` 目录，这里存放的是草稿，它不会在首页显示，请参考里面的 `2014-05-06-empty.md` 文件，新建文件名要遵循这样的格式，以日期开头，后面接着是文章的对外 url 子路径，中间以 `-` 分隔，后续标题有多个单词时也以 `-` 作为分隔符，建议只用英文单词，目前不确定中文是否可行。

需要注意的是草稿不会出现在首页列表中，如果想本地预览草稿效果，可以加 `--drafts` 参数，如下所示：

    jekyll serve --watch --drafts

### 个人信息

每篇文章都会附上个人相关信息，所以请先编辑 `_data\authors.yml` 文件，按照其中的格式新增一项，需要注意以下几点：

* 这是 YAML 格式，每行的开头是两个空格，而不是 TAB
* `author` 字段需要和你所写文章开头的 `author` 属性保持一致，这样才能正确展现
* `url` 字段可以连接到个人主页或微博等
* `intro` 是个人简介，会在每篇文章中展现
* `avatar` 是个人头像，尺寸暂定 120 x 120，请放在 `img/avatar` 目录下
    * 为何不用 gavatar？因为不是所有人都希望公开自己的邮箱，而且这样操作起来会简单些

### 图片存放地

请将图片放在 `img` 目录里，每篇文章新建一个目录，在文章中的引用方式为：

    ![](/img/<文章名>/xx.png)

### 发布

如果觉得文章可以对外展示了，就将它移到 `_posts` 目录下，提交 github 后就马上生效了。

### 小技巧

* jekyll 最终生成的文件会放在 `_site` 目录下，可以通过浏览这个目录来确认效果
* img 目录的主要用途是放图片，但也可以放其它文件静态，如 zip 等

## 写什么？

虽然对外会觉得这是团队 Blog，但实际上它是每个团队成员的个人分享，每篇文章都只代表个人观点，所以如果有什么值得分享的内容，请不要有太多顾虑，想写什么就写什么，借助这个平台来提升自己的影响力吧。

具体内容形式将包括但不限于：

* 技术介绍、经验总结
* FEX 新开源项目及升级版本介绍
* 优秀文章的翻译
* 优秀资源（书籍、开源项目）等的推荐
* 内部分享的 PPT（推荐使用 [Speaker Deck](https://speakerdeck.com/) 存放）

另外，如果你对目前界面的哪些细节不满意，也欢迎直接修改相关源码。

### 对于写作风格的约定

请参考[FEX 写作风格](https://github.com/fex-team/styleguide/blob/master/writing.md)

## 其它问题

* 文章发布前需要找谁审核么？
    * 不需要，因为每篇文章都是以个人名义发表的
* 我不是 FEX 团队成员，可以在这里发表文章么？
    * 可以，欢迎提 pull request

