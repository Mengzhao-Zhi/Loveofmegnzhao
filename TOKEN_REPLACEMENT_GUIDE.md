# 个人访问令牌替换指南

## 问题分析

当前远程 URL 中包含占位符 `YOUR_TOKEN`，需要替换为您实际生成的个人访问令牌：

```
https://YOUR_TOKEN@github.com/Mengzhao-Zhi/Loveofmegnzhao.git
```

## 解决方案

### 步骤 1：生成个人访问令牌

1. 登录 GitHub 账号
2. 进入 Settings → Developer settings → Personal access tokens → Tokens (classic)
3. 生成一个新的令牌，勾选 `repo` 权限
4. 复制生成的令牌（例如：`ghp_1234567890abcdefghijklmnopqrstuvwxyz`）

### 步骤 2：更新远程 URL

在终端中执行以下命令，将 `YOUR_ACTUAL_TOKEN` 替换为您刚才生成的个人访问令牌：

```bash
# 更新远程 URL 以包含实际令牌
git remote set-url origin https://YOUR_ACTUAL_TOKEN@github.com/Mengzhao-Zhi/Loveofmegnzhao.git

# 验证远程 URL 是否已更新
git remote get-url origin

# 推送代码到 GitHub
git push --set-upstream origin main
```

### 示例

如果您的个人访问令牌是 `ghp_1234567890abcdefghijklmnopqrstuvwxyz`，则命令应为：

```bash
git remote set-url origin https://ghp_1234567890abcdefghijklmnopqrstuvwxyz@github.com/Mengzhao-Zhi/Loveofmegnzhao.git
git push --set-upstream origin main
```

## 故障排除

### 令牌格式错误
- 确保令牌完整复制，没有多余的空格或字符
- 令牌格式通常以 `ghp_` 开头

### 权限不足
- 确保您的令牌具有 `repo` 权限
- 如果仍然失败，尝试生成一个新的令牌并确保勾选了所有必要的权限

### 网络问题
- 检查您的网络连接
- 尝试使用 SSH 格式的远程 URL 作为替代方案

## 替代方案：使用 SSH

如果 HTTPS 认证仍然失败，您可以尝试使用 SSH 密钥进行认证：

1. 生成 SSH 密钥：`ssh-keygen -t ed25519 -C "your_email@example.com"`
2. 添加 SSH 密钥到 GitHub：在 Settings → SSH and GPG keys 中添加公钥
3. 更新远程 URL：`git remote set-url origin git@github.com:Mengzhao-Zhi/Loveofmegnzhao.git`
4. 推送代码：`git push --set-upstream origin main`
