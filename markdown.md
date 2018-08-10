<!-- TOC depthFrom:1 depthTo:6 withLinks:1 updateOnSave:1 orderedList:0 -->

- [Markdown 使用](#markdown-使用)
	- [在本地合并 pull request](#在本地合并-pull-request)

<!-- /TOC -->
# Markdown 使用
## 在本地合并 pull request

Step 1: From your project repository, check out a new branch and test the changes.
```
$ git checkout -b aixingxy-patch-1 master
$ git pull https://github.com/aixingxy/Python.git patch-1
```
Step 2: Merge the changes and update on GitHub.
```
$ git checkout master
$ git merge --no-ff aixingxy-patch-1
$ git add .
$ git commit -m "PR"
$ git push origin master
```
