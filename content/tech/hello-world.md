---
title: "Hello World"
date: 2020-10-23T08:53:44+08:00
draft: false
tags:
  - hugo
  - blog
gitinfo: true
---

> 感谢OI wiki对本文的帮助[^1] 
>
> 脚注测试
>

分割线测试

---

### **撰写blog**

内容来源[^2]

之前有提到过，每个blog除了内容部分以外，还有一个很重要的是描述blog的一些属性。举例来说，blog的标题叫什么、什么时候写的blog、blog的标签是啥、主题又是啥，这些都是blog的元数据。

hugo使用markdown来描述blog的正文内容，那这些元数据如何表示呢？hugo选择在markdown文件头添加一部分信息，并管这些信息叫**front matter**。

### **blog的元数据，front matter**

为了区别front matter与正文内容，front matter使用一对 `---` 作为起止界限。这篇blog的front matter如下：

```
---
title: "使用hugo搭建个人blog"
date: 2019-07-01T09:21:57+08:00
draft: false
topics:
  - blog
  - hugo
  - personal
tags:
  - hugo
  - blog
summary: 本文介绍如何基于hugo搭建自己的个人blog，包括blog的意义、blog服务选择、hugo介绍以及使用travis进行一定程度自动化等内容。
---
这里开始就是blog的正文了。
```

可以看到front matter使用toml，支持字典与数组来描述各个属性。具体的写法也很好理解，没必要啰嗦了。

### 使用hugo new命令创建blog内容模板

如果每次创建都需要啰哩啰嗦写一些通用头比较麻烦，因此hugo给我们提供了一个`hugo new XXX`的命令，通过这个命令，可以生成一个包含front matter的md文件，至此我们就可以打开自己喜欢的markdown编辑器，开心的写blog了！

如果遇到使用gitinfo无法显示git信息的时候请使用

```
git config --global core.quotePath false
```

或者

```
git config --global core.precomposeunicode true
```

---

[^1]: 说明：本文即采用持续写作的方式创作并发布，见 [#10](https://github.com/reuixiy/io-oi.me/issues/10)
[^2]:内容来源

