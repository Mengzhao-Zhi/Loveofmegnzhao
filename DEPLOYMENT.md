# 网站部署指南：GitHub Pages

## 步骤 1：在 GitHub 上创建仓库

1. 登录您的 GitHub 账号
2. 点击右上角的 "New" 按钮创建新仓库
3. 填写仓库名称（例如：`personal-portfolio`）
4. 选择仓库类型为 "Public"（公开）
5. 点击 "Create repository" 按钮

## 步骤 2：将本地代码推送到 GitHub

在终端中执行以下命令：

```bash
# 替换为您的 GitHub 仓库 URL
git remote add origin https://github.com/your-username/your-repository.git

# 推送到 GitHub
git push -u origin main
```

## 步骤 3：启用 GitHub Pages

1. 进入 GitHub 仓库页面
2. 点击 "Settings" 选项卡
3. 在左侧菜单中选择 "Pages"
4. 在 "Source" 部分，选择分支为 "main"，目录为 "/ (root)"
5. 点击 "Save" 按钮
6. 等待几分钟，GitHub 会构建并部署您的网站
7. 部署完成后，您会看到一个绿色的提示，显示您的网站已发布在 `https://your-username.github.io/your-repository/`

## 步骤 4：访问您的网站

打开浏览器，访问 `https://your-username.github.io/your-repository/` 即可看到您的个人主页网站。

## 后续更新

如果您对网站进行了修改，只需执行以下命令即可更新 GitHub Pages：

```bash
git add .
git commit -m "Update website"
git push
```

## 注意事项

- GitHub Pages 只支持静态网站，不支持服务器端代码
- 部署可能需要几分钟时间才能生效
- 如果遇到问题，可以检查 GitHub Actions 中的构建日志
