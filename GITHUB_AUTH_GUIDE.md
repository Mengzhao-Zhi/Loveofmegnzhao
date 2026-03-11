# GitHub 认证和部署指南

## 步骤 1：生成 GitHub 个人访问令牌

1. **登录 GitHub 账号**：打开 https://github.com 并登录

2. **进入开发者设置**：
   - 点击右上角的个人头像
   - 选择 "Settings"
   - 在左侧菜单中选择 "Developer settings"

3. **创建个人访问令牌**：
   - 选择 "Personal access tokens" → "Tokens (classic)"
   - 点击 "Generate new token" → "Generate new token (classic)"
   - 填写令牌信息：
     - **Note**：输入 "Personal Portfolio Deployment"
     - **Expiration**：选择 "30 days" 或更长时间
     - **Select scopes**：勾选 `repo` 权限
   - 点击 "Generate token"

4. **复制令牌**：
   - **重要**：生成的令牌只会显示一次，立即复制并保存到安全的地方

## 步骤 2：使用令牌进行认证和推送

在终端中执行以下命令，将 `YOUR_TOKEN` 替换为您刚才生成的个人访问令牌：

```bash
# 更新远程 URL 以包含令牌
git remote set-url origin https://YOUR_TOKEN@github.com/Mengzhao-Zhi/Loveofmegnzhao.git

# 推送代码到 GitHub
git push --set-upstream origin main
```

## 步骤 3：启用 GitHub Pages

1. **进入仓库设置**：
   - 打开 https://github.com/Mengzhao-Zhi/Loveofmegnzhao
   - 点击 "Settings" 选项卡

2. **配置 GitHub Pages**：
   - 在左侧菜单中选择 "Pages"
   - 在 "Source" 部分：
     - 选择 "Branch" 为 "main"
     - 选择 "Folder" 为 "/ (root)"
   - 点击 "Save"

3. **等待部署完成**：
   - GitHub 会自动构建和部署您的网站
   - 部署过程可能需要几分钟时间
   - 完成后，您会看到一个绿色的提示，显示您的网站已发布

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

## 故障排除

### 认证失败
- 确保您的个人访问令牌有效且未过期
- 确保令牌具有 `repo` 权限
- 检查远程 URL 是否正确设置

### 推送失败
- 确保您的本地分支是最新的
- 检查是否有未提交的更改
- 验证令牌是否正确包含在远程 URL 中

### GitHub Pages 未更新
- 等待几分钟，GitHub Pages 构建可能需要时间
- 检查仓库设置中的 Pages 配置是否正确
- 检查 GitHub Actions 中的构建日志
