# Git使用指南

## 初始化及基本操作

### 初始化

```text
git init
```

### 添加进库

```text
git add .
```

### 提交修改

```text
git commit -m "xxxxxxxxx"
```

## 连接远程仓库

### 建立连接

```sh
# ssh
git remote add origin git@github.com:yourName/repositoryname.git
```

or

```sh
# http
git remote add origin https://github.com/yourName/repositoryname.git
```

### 上传、下载

```sh
# push single branch
git push origin branch_name

# pull single branch
git pull origin branch_name
```

### 对所有分支进行操作

#### git将多个分支同步到github

1. 一次性推送所有分支。在本地仓库目录下，执行`git push --all origin`命令，可以将本地仓库的所有分支一次性推送到远程仓库origin。如果远程仓库中没有对应的分支，会自动创建。
2. 分别推送每个分支。在本地仓库目录下，切换到要推送的分支，执行`git push origin branchname`命令，可以将本地仓库的指定分支推送到远程仓库origin。如果远程仓库中没有对应的分支，会自动创建。
3. 在github网站上合并分支。在github上创建一个pull request，选择要合并的源分支和目标分支，然后点击Merge pull request按钮，可以将源分支的内容合并到目标分支。

#### git将多个分支同步到本地

1. 执行`git pull --all`命令，可以将远程仓库的所有分支拉取到本地仓库，并与对应的本地分支合并。这需要本地仓库已经跟踪了所有远程分支。
2. 执行`git remote update`命令，可以将远程仓库的所有分支信息更新到本地仓库，但不会合并。然后可以切换到要更新的本地分支，执行`git pull origin branchname`命令，将远程分支的内容拉取并合并到本地分支。
3. 执行`git fetch --all`命令，可以将远程仓库的所有分支内容拉取到本地仓库，但不会合并。然后可以切换到要更新的本地分支，执行`git merge origin/branchname`命令，将远程分支的内容合并到本地分支。

## 为一个 Git 本地仓库添加两个远程仓库地址

要为一个 Git 本地仓库添加两个远程仓库地址，可以使用以下命令：

1. 首先，添加第一个远程仓库地址：

    ```bash
    git remote add origin1 <URL1>
    ```

   其中，`origin1` 是您为第一个远程仓库设置的名称，可以自定义。`<URL1>` 是第一个远程仓库的 URL 地址。

2. 接下来，添加第二个远程仓库地址：

    ```bash
    git remote add origin2 <URL2>
    ```

   同样，`origin2` 是您为第二个远程仓库设置的名称，可以自定义。`<URL2>` 是第二个远程仓库的 URL 地址。

现在，您的本地仓库就有了两个远程仓库地址。您可以使用这些名称来引用不同的远程仓库，例如 `origin1` 和 `origin2`。

要推送到特定的远程仓库，可以使用以下命令：

```bash
git push <remote-name> <branch-name>
```

其中，`<remote-name>` 是远程仓库的名称（例如 `origin1` 或 `origin2`），`<branch-name>` 是要推送的分支名称。

同样地，在执行推送操作之前，请确保您已经备份了重要的分支或确认了要推送的分支的更改。

您可以使用以下命令查看远程仓库的列表：

```bash
git remote -v
```

这将显示所有已配置的远程仓库及其对应的 URL 地址。

## 修改远程仓库地址

```bash
git remote set-url origin https://github.com/your-username/your-repo.git
```

**NOTE:** 将命令中的origin替换为你实际使用的远程仓库名称，并将新地址替换为你希望使用的新仓库地址。
