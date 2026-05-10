---
description: "工作区域指令：Git提交规则和文档格式标准"
---

# Copilot 工作区域指令

## Git 提交规则

创建提交信息时，请遵循以下指南：

- 主题行使用祈使语气（例如："Add feature" 而不是 "Added feature"）
- 主题行保持在50个字符以内
- 主题和正文之间使用空行
- 正文换行在72个字符处
- 解释是什么和为什么，而不是如何
- 适当时引用问题编号（例如："Fix #123"）

示例：
```
Add user authentication feature

- Implement login endpoint with JWT tokens
- Add password hashing with bcrypt
- Create user registration form

Closes #456
```

## 文档格式规则

对于所有文档文件（Markdown 等）：

- 使用一致的标题级别（从 # 开始，然后 ## 等）
- 为代码片段使用代码块，并带有适当的语言标签
- 使用项目符号列表
- 保持行长在80个字符以内以提高可读性
- 使用正确的Markdown语法链接、图像和表格
- 为图像包含替代文本
- 使用描述性链接文本而不是"点击这里"

### Markdown 特定规则

- 使用 `内联代码` 表示代码引用
- 使用 ```language 块表示多行代码
- 使用 > 表示块引用
- 适当使用 **粗体** 和 *斜体*
- 确保标题和列表周围有适当的间距

### 文件组织

- 将相关文件保存在适当的目录中
- 使用描述性文件名
- 遵循项目的现有结构模式

## 自动提交规则

每次修改文档时，请自动提交Git更改，并写清楚提交说明：

- 在修改文档后，立即运行 `git add .` 和 `git commit -m "提交说明"`
- 提交说明应简洁明了，描述修改的内容（例如："更新README.md中的格式" 或 "修复文档中的拼写错误"）
- 如果有多个文件更改，使用列表形式描述每个更改
- 确保提交信息使用中文，并遵循上述Git提交规则

## Git 提交信息语言规则

所有 Git 提交信息必须使用**中文**编写。包括主题行和正文内容。

示例：
```
删除默认的 Hexo hello-world 示例文章
```
```
优化文章标题并精简构建日志

- 重命名 Android-Biometric 文章标题，添加描述性副标题
- 精简 sbt-encoding-issue 文章标题
- 将 Bulletproofs-Rust 构建日志从 300+ 行精简为简短摘要
- 移除 Bulletproofs 文章中不相关的文档链接
```