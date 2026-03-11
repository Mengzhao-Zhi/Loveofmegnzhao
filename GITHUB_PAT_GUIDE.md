# GitHub 个人访问令牌 (PAT) 使用指南

## 步骤 1：生成个人访问令牌

1. 登录您的 GitHub 账号
2. 点击右上角的个人头像，选择 "Settings"
3. 在左侧菜单中选择 "Developer settings"
4. 选择 "Personal access tokens" → "Tokens (classic)"
5. 点击 "Generate new token" → "Generate new token (classic)"
6. 填写以下信息：
   - **Note**：输入一个描述性的名称，例如 "Personal Portfolio Deployment"
   - **Expiration**：选择令牌的有效期，建议选择 "30 days" 或更长时间
   - **Select scopes**：勾选以下权限：
     - `repo`（所有 repo 相关权限）
     - `workflow`（如果需要 GitHub Actions）
7. 点击 "Generate token" 按钮
8. **重要**：复制生成的令牌，因为您将无法再次看到它

## 步骤 2：使用个人访问令牌推送到 GitHub

在终端中执行以下命令，当提示输入密码时，粘贴您刚才生成的个人访问令牌：

```bash
# 首先确保远程仓库已正确添加
git remote set-url origin https://github.com/Mengzhao-Zhi/Loveofmegnzhao.git

# 推送到 GitHub
git push -u origin main
```

## 步骤 3：启用 GitHub Pages

1. 进入 GitHub 仓库页面：https://github.com/Mengzhao-Zhi/Loveofmegnzhao
2. 点击 "Settings" 选项卡
3. 在左侧菜单中选择 "Pages"
4. 在 "Source" 部分，选择分支为 "main"，目录为 "/ (root)"
5. 点击 "Save" 按钮
6. 等待几分钟，GitHub 会构建并部署您的网站
7. 部署完成后，您会看到一个绿色的提示，显示您的网站已发布

## 步骤 4：访问您的网站

部署完成后，您的网站将可以通过以下 URL 访问：
https://mengzhao-zhi.github.io/Loveofmegnzhao/

## 后续更新

如果您对网站进行了修改，只需执行以下命令即可更新：

```bash
git add .
git commit -m "Update website"
git push
```

## 注意事项

- 个人访问令牌是敏感信息，请妥善保管，不要分享给他人
- 如果令牌过期，您需要重新生成一个新的令牌
- 部署可能需要几分钟时间才能生效
- 如果遇到问题，可以检查 GitHub Actions 中的构建日志
