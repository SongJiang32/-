# Git guidance

How to use git upload your files?

## Preparation

1. 生成SSH密钥

```
ssh-keygen -t ed25519 -C "your_email@example.com"
```

> ed25519为加密算法
> 
> 按Enter接受默认位置
> 
> 设置密码（可选）

2. 复制公钥并添加

```
cat ~/.ssh/id_ed25519.pub
```

> 登录 GitHub → 点击右上角头像 → Settings
>
> 左侧菜单 → SSH and GPG keys
>
> 点击 New SSH key
>
> 填写：
 Title: My Ubuntu Laptop（任意描述）
>
 Key type: Authentication Key
>
 Key: 粘贴刚才复制的整个公钥内容


3. 测试连接

```
ssh -T git@github.com
```

>如果看到类似这样的消息，说明成功:
>
> Hi yourName! You've successfully authenticated, but GitHub does not provide shell access.

## Setting in the project

```
git init
```

> 配置用户信息 

```
git config user.name "yourName"
git config user.email "your_email@example.com"
```

> 添加文件到暂存区

```
git add .
```

> 查看暂存状态，绿色表示成功

```
git commit -m "任意说明"
```

添加远程仓库

```
git remote add origin git@github.com:yourName/yourRepository.git
```

> 修改远程URL为SSH

```
git remote set-url origin git@github.com:yourName/yourRepository.git
```

## 查看分支

```
git branch
```

> 重命名本地分支：git branch -M newBranch
> 切换分支git checkout -b main

## 上传

```
git push -u origin main
```

## 后续更新代码

```
git add --all
git commit -m "描述你的更改"
git push
```
