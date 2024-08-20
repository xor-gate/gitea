---
date: "2024-04-10T22:21:00+08:00"
title: "变量"
slug: "actions-variables"
sidebar_position: 25
draft: false
toc: false
menu:
  sidebar:
    parent: "actions"
    name: "变量"
    sidebar_position: 25
    identifier: "actions-variables"
---

## 变量

您可以创建用户、组织和仓库级别的变量。变量的级别取决于创建它的位置。当创建变量时，变量的名称会被
转换为大写，在yaml文件中引用时需要使用大写。

### 命名规则

以下规则适用于变量名：

- 变量名称只能包含字母数字字符 (`[a-z]`, `[A-Z]`, `[0-9]`) 或下划线 (`_`)。不允许使用空格。
- 变量名称不能以 `GITHUB_` 和 `GITEA_` 前缀开头。
- 变量名称不能以数字开头。
- 变量名称不区分大小写。
- 变量名称在创建它们的级别上必须是唯一的。
- 变量名称不能为 `CI`。

### 使用

创建配置变量后，它们将自动填充到 `vars` 上下文中。您可以在工作流中使用类似 `${{ vars.VARIABLE_NAME }}` 这样的表达式来使用它们。

### 优先级

如果同名变量存在于多个级别，则级别最低的变量优先。
仓库级别的变量总是比组织或者用户级别的变量优先被选中。