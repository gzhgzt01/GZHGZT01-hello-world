# GitHub 学习笔记

这是我的 GitHub 第二课。
## 第二课：文件与路径
# GitHub 学习笔记

---

# 第一课：GitHub 核心工作流

## 1. 本课目标

理解并亲手完成 GitHub 最基本的开发工作流：

main
→ 创建 Branch
→ 修改文件
→ Commit
→ 创建 Pull Request
→ 查看 Diff
→ Merge
→ 删除已完成的 Branch

---

## 2. 核心概念

### Repository（仓库）

Repository，简称 Repo。

可以理解为一个项目在 GitHub 中的完整仓库。

里面不仅有文件和代码，还保存 Branch、Commit、Pull Request、版本历史等信息。

---

### Main（主分支）

main 通常是项目的主要分支。

可以把它理解为项目当前正式版本所在的主要开发路线。




### Branch（分支）

Branch 是从项目当前状态分出来的一条独立开发路线。

例如：

main
└── learn-readme

我们可以在 learn-readme 中修改文件，而暂时不影响 main。

Branch 的重要作用：

先安全修改和测试
→ 检查修改
→ 确认没问题
→ 再 Merge 回 main

---

### Commit（提交 / 版本记录）

Commit 不是“修改”本身。

修改文件之后，通过 Commit 把这一批修改正式记录进 Git 的版本历史。

每个 Commit 都有自己的标识，例如：

411b32a

这个标识叫 Commit SHA。

Commit message 应该简单、准确地说明这次修改做了什么。

---

### Diff（差异 / 改动对比）

Diff 用来查看修改前和修改后到底发生了什么变化。

常见表示：

- 红色 / `-` ：删除的内容
- 绿色 / `+` ：增加的内容

例如：

-欢迎浏览产品目录
+欢迎浏览产品电子书
+返回主目录

表示：

删除 1 行
增加 2 行

Diff 主要按照“行”比较。

空白行如果是新增加的，也可能计入 `+`。

重要原则：

改动数量只是提醒，
Diff 的具体内容才是判断修改是否正确的证据。

---

### Pull Request（PR）

Pull Request，简称 PR。

可以理解为：

“我这个 Branch 的修改已经做好了，请检查这些修改是否应该合并进 main。”

创建 PR 不等于已经进入 main。

PR 是审核和讨论修改的地方。

---

### Merge（合并）

Merge 是把一个 Branch 的修改正式合入目标 Branch。

例如：

learn-readme
↓ Merge
main

Merge 以后，修改才正式进入 main。

所以：

Commit ≠ Merge
PR ≠ Merge

---

## 3. 第一课完整工作流

main
↓
创建 Branch
↓
修改文件
↓
Commit
↓
创建 PR
↓
检查 Diff
↓
确认修改正确
↓
Merge
↓
删除已经完成任务的 Branch

---

## 4. 为什么 Merge 后可以删除 Branch？

Branch 的任务完成并 Merge 进入 main 后，通常可以删除这个临时 Branch。

删除已经 Merge 的 Branch：

不会删除已经进入 main 的成果。

可以理解为：

Branch 是临时施工路线，
Merge 后成果已经进入正式道路 main，
临时路线可以清理。

---

## 5. Codex 使用场景

以后 Codex 可能告诉我：

Created branch feature/gallery
Changed 4 files
Created commit a82f731
Opened PR #18
All checks passed

我应该理解：

feature/gallery
= Codex 创建的工作 Branch

Changed 4 files
= 实际修改了 4 个文件

a82f731
= 一个 Commit 的 SHA

PR #18
= 第 18 个 Pull Request，修改正在等待审核/合并

All checks passed
= 自动检查通过，但不代表我应该无脑 Merge

Merge 前仍然应该检查 Diff。

---

## 6. 第一课最重要的判断原则

Codex 说“完成了”，不代表修改一定正确。

应该检查：

它修改了哪些文件？
增加了什么？
删除了什么？
有没有修改不应该修改的内容？

最终以 GitHub 中看到的实际 Diff 为依据。

---

## 7. 第一课核心英文

Repository / Repo
仓库

Branch
分支

Main
主分支

Commit
提交 / 版本记录

Diff
差异 / 改动对比

Pull Request / PR
拉取请求 / 合并申请

Merge
合并

Changes
修改 / 更改

---

## 8. 第一课一句话记忆

Branch 是工作路线，
Commit 是版本记录，
PR 是审核申请，
Diff 是实际改动，
Merge 是最终合并。

---

# 第二课：看懂一个 Repository

## 1. 本课目标

学会看懂 GitHub Repository 的基本结构，并能够通过历史记录追查文件和代码发生过什么变化。

---

## 2. Repository 的基本组成

一个 Repository 不只是一堆代码。

它包含：

Repository
├── Files / Folders
├── Branches
├── Commit History
├── Pull Requests
├── Issues
└── Actions

本课主要学习：

File
Folder / Directory
Path
README
Markdown
History
Commit
SHA
Parent
Diff
Blame

以及文件的：

Create
Modify
Rename
Delete

---

## 3. File 和 Folder

File
= 文件

Folder / Directory
= 文件夹 / 目录

例如：

Repository
├── README.md
├── docs/
│   └── GitHub学习笔记.md
└── images/
    └── products/
        └── logo.png

---

## 4. Path（路径）

Path 表示一个文件在 Repository 中的位置。

例如：

images/products/logo.png

可以理解成：

images 文件夹
→ products 文件夹
→ logo.png 文件

注意：

文件路径中的大小写不要随意改变。

---

## 5. README.md

README 可以理解为：

Read Me
= “先读我”

进入一个陌生 Repository 时，通常应该先阅读 README。

README 经常说明：

项目是干什么的
怎么安装
怎么使用
需要什么环境
有哪些注意事项

---

## 6. Markdown

`.md` 通常表示 Markdown 文件。

例如：

README.md

Markdown 是一种简单的文本排版格式。

例如：

# GitHub 学习笔记

其中：

`#`
表示一级标题。

---

## 7. Preview、Code、Blame

### Preview

看 Markdown 渲染后的最终效果。

例如：

`# GitHub 学习笔记`

在 Preview 中会显示成大标题。

### Code

看文件实际保存的原始内容。

例如可以看到：

`# GitHub 学习笔记`

注意：

Code 页面显示的不一定是程序代码。

README 的 Code 是 Markdown 原文。

### Blame

逐行追查文件内容。

可以查看：

这一行最后是谁修改的
什么时候修改的
来自哪个 Commit

记忆：

Preview = 看效果
Code = 看原文
Blame = 查来源

---

## 8. Repository History 和 File History

Repository History：

整个仓库的 Commit 历史。

File History：

只显示与当前这个文件有关的 Commit。

例如：

Repository 一共有 100 个 Commits

logo.png 的 History 只有 3 个 Commits

并不矛盾。

说明整个项目发生过 100 次 Commit，
其中只有 3 次涉及 logo.png。

---

## 9. Commit SHA

每个 Commit 都有自己的标识。

例如：

411b32a
59ca4c2
bd8d128

可以把 SHA 理解为 Commit 的“身份证号”。

它可以精确定位某一次 Commit。

---

## 10. Parent

Parent 表示当前 Commit 的上一个提交。

例如：

59ca4c2
↓ 修改文件
bd8d128

那么：

bd8d128 的 Parent
= 59ca4c2

Parent 可以帮助追查修改发生之前的状态。

---

## 11. Browse files

Browse files 可以查看：

某一个 Commit 当时整个 Repository 是什么状态。

例如：

当前 main 中 say hello 已经被删除。

但进入删除之前的 Commit：

cc04b8e

再使用 Browse files，

仍然可以看到当时存在的：

say hello

说明：

当前版本删除文件
≠
过去的历史版本也被删除。

---

## 12. 当前 main 和历史 Commit

main 是持续向前发展的 Branch。

例如：

cc04b8e
↓
887d820
↑
main 当前指向较新的版本

在旧 Commit `cc04b8e` 中：

say hello 存在

在最新 main 中：

say hello 已删除

切换到旧 Commit 查看文件：

不等于把 main 恢复到了旧版本。

只是查看那个历史时刻的 Repository 状态。

---

## 13. 文件的四种基本变化

### Create

创建文件。

例如：

docs/GitHub学习笔记.md

---

### Modify

修改已有文件内容。

Diff 会显示增加和删除的行。

例如：

+1
-1

---

### Rename

修改文件名或路径。

例如：

docs/学习笔记.md

变成：

docs/GitHub学习笔记.md

如果内容没有变化，GitHub 可能显示：

File renamed without changes

说明：

文件内容没有变化，
但文件名 / Path 发生了变化。

---

### Delete

删除文件。

例如 say hello 原来只有：

hello world !

删除后 Diff：

+0
-1

并显示：

This file was deleted.

删除当前版本中的文件，
并不意味着 Git 历史中的旧文件也消失。

---

## 14. Diff 按行统计

例如文件原来：

# GitHub 学习笔记

这是我的 GitHub 第二课。

一共有：

第1行：标题
第2行：空白行
第3行：正文

空白行也是一行。

但是 Diff 统计的是：

“相比上一个版本，增加或删除了哪些行。”

不是统计文件现在总共有多少行。

---

## 15. 使用 Blame 调查问题

假设一个文件有 500 行代码。

发现第 327 行有问题。

最有效的方法之一：

找到文件
↓
Blame
↓
定位第327行
↓
找到对应 Commit
↓
查看作者和时间
↓
打开 Commit
↓
查看 Diff
↓
必要时查看 Parent
↓
Browse files 查看修改前状态

---

## 16. History、Blame、Diff 的区别

History：

回答：
“这个文件以前经历过哪些 Commit？”

Blame：

回答：
“这一行最后是谁、在哪次 Commit 改的？”

Diff：

回答：
“某一次修改具体增加、删除、改变了什么？”

所以排查问题时经常使用：

发现可疑行
→ Blame
→ Commit
→ Diff
→ Parent
→ Browse files

---

## 17. Codex 使用场景

假设 Codex 告诉我：

“只修改了 docs/guide.md。”

但 GitHub 显示：

4 files changed
+83 -41

涉及：

docs/guide.md
src/login.js
config/database.js
images/logo.png

不能因为 `+83 -41` 就直接判断 Codex 一定做错。

因为：

+83 -41
只是表示增加和删除了多少行。

真正需要调查的是：

为什么 Codex 声称只修改一个文件，
实际上却有四个文件发生变化？

应该继续检查这些文件的 Diff，
然后再决定是否 Merge。

---

## 18. 第二课核心英文

File
文件

Folder / Directory
文件夹 / 目录

Path
路径

README
项目说明文件

Markdown / MD
Markdown 文档格式

Preview
预览

Code
原始内容 / 代码视图

History
历史

SHA
Commit 标识

Parent
父提交 / 上一个提交

Blame
逐行追踪

Rename
重命名

Delete
删除

Browse files
浏览某个历史 Commit 当时的文件

Create
创建

Modify / Modified
修改 / 已修改

---

## 19. 第二课一句话记忆

Repository 不只是当前的一堆文件，
它还保存着项目如何一步一步变成现在这个样子的历史。

发现问题时：

Path 找位置，
History 看历史，
Blame 查某一行，
Diff 看具体变化，
SHA 锁定 Commit，
Parent 找上一个版本，
Browse files 看当时整个仓库。
main
│
├── docs/
│   └── GitHub学习笔记.md
│
└── 创建 Branch：lesson-03
        ↓
   编辑 GitHub学习笔记.md
        ↓
   添加“第三课”内容
        ↓
      Commit
        ↓
       PR
        ↓
      Diff
        ↓
      Merge
        ↓
       main
