+++
title = 'Windows中Codex沙箱账户的删除'
date = '2026-07-15T22:01:10+08:00'
description = ''
tags = ['Agent']
categories = ['Tech']
draft = false
+++

首先需要删除Codex的帐户。打开终端，输入以下命令：
```nushell
net user
```
找到
```nushell
CodexSandboxOnline
CodexSandboxOffline
```
执行以下命令删除账户：
```nushell
net user CodexSandboxOnline /delete
net user CodexSandboxOffline /delete
```

接下来删除Codex的用户组，输入：
```nushell
net localgroup 
```
找到
```nushell
*CodexSandboxUsers
```
执行以下命令删除用户组：
```nushell
net localgroup CodexSandboxUsers /delete
```
