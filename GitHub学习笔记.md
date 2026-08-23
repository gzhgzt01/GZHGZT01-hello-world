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
## 第三课：Git 本地仓库与远程仓库
这是在 GitHub 远程端添加的内容。
# 第三课：Git、GitHub 与本地电脑

## 1. 本课目标

理解 Git、GitHub、本地仓库和远程仓库之间的关系。

掌握两种建立 Git 项目的基本路线：

路线一：
GitHub 已有 Repository
→ Clone 到本地
→ 修改
→ Add
→ Commit
→ Push 回 GitHub

路线二：
本地普通文件夹
→ git init
→ 创建 / 修改文件
→ Add
→ Commit
→ 添加 Remote
→ Push 到 GitHub

---

## 2. 核心概念

### Git

Git 是版本控制工具。

它可以记录项目一次次发生的变化，包括：

- 哪些文件发生变化
- 增加了什么
- 删除了什么
- 谁创建了 Commit
- Commit 的历史关系

Git ≠ GitHub。

即使没有 GitHub，Git 也可以在本地电脑上进行版本管理。

---

### GitHub

GitHub 是托管 Git Repository 和进行协作的平台。

可以简单记忆：

Git = 管版本
GitHub = 托管和协作

---

### Local

Local = 本地。

表示自己的电脑以及电脑上的 Git Repository。

---

### Remote

Remote = 远程。

表示与本地 Repository 建立连接的远程 Repository，例如 GitHub 上的 Repository。

---

### Clone

Clone = 克隆。

当 GitHub 已经存在 Repository 时，可以使用：

git clone 仓库地址

把 Repository 克隆到本地。

Clone 不只是下载当前文件，还会建立本地 Git Repository，并取得 Git 版本历史。

记忆：

已有 Repository，要拿到本地
→ Clone

---

### git init

init = initialize = 初始化。

当电脑上只有普通文件夹，还不是 Git Repository 时，可以执行：

git init

让 Git 开始管理当前文件夹。

注意：

git init 管理的是执行命令时所在的当前目录。

所以执行前一定要确认 CMD 当前 Path。

记忆：

本地普通文件夹，要开始使用 Git
→ git init

---

## 3. Local 与 Remote 的基本关系

基本模型：

Local Repository
↕
Remote Repository

本地修改后：

Working Tree
↓
git add
↓
Staging Area
↓
git commit
↓
Local Repository
↓
git push
↓
GitHub Remote

远程有更新时：

GitHub Remote
↓
git fetch / git pull
↓
Local Repository

---

## 4. Working Tree / Working Directory

Working Tree / Working Directory = 工作区。

就是电脑上当前真正能够打开和修改的项目文件。

当：

git status

显示：

working tree clean

表示当前工作区没有尚未提交的新修改。

---

## 5. git status

git status 用来查看当前 Git 状态。

例如：

On branch lesson-03

表示：

当前位于 lesson-03 Branch。

如果显示：

nothing to commit, working tree clean

表示：

没有尚未 Commit 的修改。

如果显示：

Untracked files

表示：

Git 发现了新文件，但还没有开始跟踪它。

---

## 6. Untracked

Untracked = 未跟踪。

例如新建：

README.md

Git 可以发现这个文件存在，但它还没有进入版本管理。

状态可能显示：

Untracked files:
README.md

执行：

git add README.md

以后，文件就进入 Staging Area。

---

## 7. Staging Area

Staging Area = 暂存区。

可以理解成：

“准备进入下一次 Commit 的修改”。

流程：

修改 / 创建文件
↓
git add
↓
Staging Area
↓
git commit
↓
Local Repository

当 git status 显示：

Changes to be committed

表示修改已经进入暂存区，准备 Commit。

---

## 8. git add

git add 用来把指定修改加入 Staging Area。

例如：

git add README.md

表示：

把 README.md 当前的修改准备放进下一次 Commit。

注意：

git add ≠ Commit

Add 只是进入暂存区。

---

## 9. git commit

git commit 把暂存区中的修改正式记录进本地 Git 历史。

例如：

git commit -m "创建README文件"

其中：

-m

表示直接指定 Commit message。

重要：

Commit 默认发生在本地。

git commit ≠ 上传到 GitHub。

---

## 10. Root Commit

Root Commit = 一个 Repository 历史中的第一个 Commit。

例如：

3748606 (root-commit)

表示：

这是这个 Repository 的第一个 Commit。

因为它前面没有 Commit，所以没有 Parent。

---

## 11. HEAD

HEAD 可以暂时理解为：

“我当前正在工作的 Git 位置 / Branch”。

例如：

HEAD -> main

表示：

当前正在 main Branch 上工作。

git branch 中：

* lesson-03

前面的 * 也表示当前所在 Branch。

git status 中：

On branch lesson-03

也是同一个意思。

---

## 12. main 与 origin/main

main：

本地的 main Branch。

origin/main：

本地 Git 保存的“远程 origin 上 main Branch 的最近已知状态”。

刚 Clone 或同步完成时可能：

HEAD
↓
main
↓
某个 Commit
↑
origin/main

表示本地与远程当前处于同步状态。

---

## 13. origin

origin 是给 Remote Repository 起的一个本地名称。

它通常是默认使用的远程仓库名称。

origin ≠ “原来的版本”
origin ≠ Branch
origin ≠ GitHub 用户名

例如：

git remote add origin 仓库地址

表示：

添加一个 Remote，并把它命名为 origin。

---

## 14. git remote

查看 Remote：

git remote -v

可能看到：

origin  仓库地址 (fetch)
origin  仓库地址 (push)

表示：

本地 Repository 已经知道从哪里获取远程内容，以及向哪里 Push。

---

## 15. Push

Push = 推送。

把本地 Commit 推送到 Remote Repository。

例如：

git push -u origin lesson-03

表示：

把本地 lesson-03 推送到名为 origin 的远程 Repository，并建立跟踪关系。

注意：

Push ≠ Merge

把 lesson-03 Push 到 GitHub，只会让 GitHub 上出现 lesson-03。

不会自动进入 main。

---

## 16. -u

例如：

git push -u origin main

其中：

-u

用来建立本地 Branch 与对应远程 Branch 的跟踪关系。

例如：

本地 main
↕
origin/main

建立以后，后续通常可以直接使用：

git push

Git 已经知道这个 Branch 对应哪个远程 Branch。

---

## 17. Fetch

Fetch = 获取远程最新信息。

例如：

git fetch

它会更新本地 Git 对 Remote 的认识，但不会直接把远程修改整合进当前本地 Branch。

本课实验：

GitHub 上 lesson-03 新增了一个 Commit。

本地第一次执行：

git status

仍然显示 up to date。

执行：

git fetch

以后，本地才发现：

Your branch is behind 'origin/lesson-03' by 1 commit

说明：

本地 Branch 比远程落后 1 个 Commit。

---

## 18. Pull

Pull = 从 Remote 获取更新并整合到当前本地 Branch。

例如：

git pull

本课实验：

先在 GitHub 网页修改 GitHub学习笔记.md 并 Commit。

然后本地：

git fetch
↓
发现远程多 1 个 Commit
↓
git pull
↓
远程新增内容真正出现在电脑的本地文件中

记忆：

Fetch = 先获取远程最新信息
Pull = 获取并整合到当前本地 Branch
Push = 把本地 Commit 推到 Remote

---

## 19. Branch 的本地与远程关系

本地创建：

git switch -c lesson-03

此时：

lesson-03 只存在于本地。

第一次执行：

git push -u origin lesson-03

以后：

Local                     Remote

lesson-03  ←──────────→  origin/lesson-03

建立跟踪关系。

---

## 20. 两种创建 Repository 的路线

### 路线 A：GitHub 已经有 Repository

GitHub Repository
↓
git clone
↓
Local Repository
↓
修改文件
↓
git add
↓
git commit
↓
git push
↓
GitHub

---

### 路线 B：项目先存在于本地

普通文件夹
↓
git init
↓
Git Repository
↓
创建 / 修改文件
↓
git add
↓
git commit
↓
git remote add origin ...
↓
git push -u origin main
↓
GitHub

重要：

Clone 和 Init 不是严格的相反操作。

Clone：
已有 Git Repository → 克隆到本地

Init：
普通本地文件夹 → 初始化成 Git Repository

真正与 Pull 方向相反的是 Push。

---

## 21. 本课实际操作记录

本课实际完成：

1. 检查 Git 是否安装：

git --version

2. 查看 Git 作者配置：

git config --global user.name
git config --global user.email

3. 创建 github-projects 文件夹。

4. 从 GitHub Clone：

GZHGZT01-hello-world

5. 使用：

git log --oneline

验证 Clone 得到的不只是文件，还有 Commit History。

6. 创建本地 Branch：

lesson-03

7. 在本地修改：

GitHub学习笔记.md

8. 使用：

git status
git diff
git add
git commit

完成本地 Commit。

9. 使用：

git push -u origin lesson-03

第一次把本地 Branch 推送到 GitHub。

10. 在 GitHub 网页修改 lesson-03 并 Commit。

11. 本地使用：

git fetch

发现本地落后远程 1 个 Commit。

12. 使用：

git pull

把 GitHub 上的修改同步到本地。

13. 创建全新的本地项目：

git-local-pracitce

14. 使用：

git init

把普通文件夹变成 Git Repository。

15. 创建 README.md。

16. 观察 README.md：

Untracked
↓
git add
↓
Staged
↓
git commit
↓
Root Commit

17. 在 GitHub 创建空 Repository。

18. 使用：

git remote add origin ...

建立 Local 与 Remote 的关系。

19. 把 master 改名为 main。

20. 使用：

git push -u origin main

把一个从本地诞生的 Repository 第一次 Push 到 GitHub。

---

## 22. 网络代理问题

本课 Clone GitHub 时曾出现：

Failed to connect to github.com port 443

以及：

Connection was reset

排查发现：

浏览器可以访问 GitHub，
但 CMD / Git 不能直接访问。

电脑使用 U1s1 VPN。

本机代理：

127.0.0.1:7892

测试：

curl -I -x http://127.0.0.1:7892 https://github.com

返回：

200 OK

说明代理可以正常访问 GitHub。

随后设置 Git：

git config --global http.proxy http://127.0.0.1:7892

查看：

git config --global http.proxy

以后如果 U1s1 的本地代理端口发生变化，需要检查 Git 的代理配置。

127.0.0.1 表示当前电脑自己（localhost）。

7892 是当前 U1s1 提供的本地代理端口，不是 Wi-Fi 分配的端口。

---

## 23. 容易混淆和出错的地方

Git ≠ GitHub

Commit ≠ Push

Push ≠ Merge

Add ≠ Commit

Clone ≠ Download ZIP

Clone ≠ Init

Fetch ≠ Pull

main ≠ origin/main

origin ≠ 原来的版本

HEAD ≠ 某个固定 Branch

Remote ≠ 一定是 GitHub，GitHub只是常见 Remote 托管平台之一

执行 git init 前必须确认当前 Path。

CMD 中输入 Git 命令时要注意拼写：

status
不是 statu

pull
不是 puss

---

## 24. Codex 使用场景

以后看到 Codex 输出：

git status

应该理解：

Codex 正在检查当前 Repository 状态。

看到：

git add ...

应该理解：

Codex 正在选择哪些修改进入下一次 Commit。

看到：

git commit ...

应该理解：

Codex 正在创建本地版本记录。

看到：

git push

应该理解：

Codex 准备把本地 Commit 推送到 Remote。

看到：

git fetch

应该理解：

Codex 正在获取 Remote 的最新信息。

看到：

git pull

应该理解：

Codex 正在把 Remote 更新获取并整合到本地。

因此不能只看 Codex 说：

Done

还应该知道它的 Git 操作目前进行到了哪一步。

---

## 25. 本课核心英文

Git
版本控制工具
使用场景：管理项目版本历史

Local
本地
使用场景：自己的电脑 / 本地 Repository

Remote
远程
使用场景：GitHub 等远程 Repository

Clone
克隆
使用场景：把已有 Repository 克隆到本地

Init / Initialize
初始化
使用场景：把普通文件夹初始化成 Git Repository

Working Tree / Working Directory
工作区
使用场景：实际修改项目文件的地方

Untracked
未跟踪
使用场景：新文件尚未纳入 Git 跟踪

Stage / Staging Area
暂存 / 暂存区
使用场景：准备进入下一次 Commit 的修改

Add
添加到暂存区
使用场景：git add

Status
状态
使用场景：检查 Repository 当前状态

HEAD
当前 Git 位置指针
使用场景：判断当前在哪个 Branch / Commit

Origin
远程 Repository 的常用默认名称
使用场景：origin/main、git push origin main

Push
推送
使用场景：Local → Remote

Fetch
获取远程信息
使用场景：更新本地对 Remote 状态的认识

Pull
拉取并整合
使用场景：Remote → Local

Root Commit
根提交 / 第一个提交
使用场景：Repository 历史中的第一次 Commit

Track / Tracking
跟踪关系
使用场景：本地 Branch 对应远程 Branch

Up to date
已是最新
使用场景：本地 Branch 与已知 Remote 状态一致

Behind
落后
使用场景：本地 Branch 比 Remote 少 Commit

---

## 26. 一句话记忆

Git 管版本，GitHub 托管仓库。

已有仓库拿到本地用 Clone；
本地普通文件夹开始用 Git 用 Init。

本地修改：

Working Tree
→ Add
→ Staging Area
→ Commit
→ Local Repository
→ Push
→ Remote

远程更新：

Remote
→ Fetch
→ 知道远程变化
→ Pull
→ 更新本地

Commit 是记录，
Push 是上传，
Pull 是拉回，
Merge 是合并。
