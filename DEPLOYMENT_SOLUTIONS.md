# 网站部署解决方案

## 方案 1：使用个人访问令牌进行认证

### 步骤 1：生成个人访问令牌
1. 登录 GitHub 账号
2. 进入 Settings → Developer settings → Personal access tokens → Tokens (classic)
3. 生成一个新的令牌，勾选 `repo` 权限
4. 复制生成的令牌

### 步骤 2：使用令牌推送代码
在终端中执行以下命令，将 `YOUR_TOKEN` 替换为您的个人访问令牌：

```bash
# 更新远程 URL 以包含令牌
git remote set-url origin https://YOUR_TOKEN@github.com/Mengzhao-Zhi/Loveofmegnzhao.git

# 推送代码
git push --set-upstream origin main
```

## 方案 2：使用 SSH 密钥进行认证

### 步骤 1：生成 SSH 密钥
```bash
# 生成 SSH 密钥
ssh-keygen -t ed25519 -C "your_email@example.com"

# 启动 SSH 代理
eval "$(ssh-agent -s)"

# 添加 SSH 密钥到代理
ssh-add ~/.ssh/id_ed25519
```

### 步骤 2：在 GitHub 上添加 SSH 公钥
1. 复制 SSH 公钥内容：`cat ~/.ssh/id_ed25519.pub`
2. 登录 GitHub，进入 Settings → SSH and GPG keys
3. 点击 "New SSH key"，粘贴公钥并保存

### 步骤 3：更新远程 URL 并推送
```bash
# 更新远程 URL 为 SSH 格式
git remote set-url origin git@github.com:Mengzhao-Zhi/Loveofmegnzhao.git

# 推送代码
git push --set-upstream origin main
```

## 方案 3：使用 GitHub Desktop

1. 下载并安装 GitHub Desktop：https://desktop.github.com/
2. 登录您的 GitHub 账号
3. 克隆仓库：File → Clone repository → URL
4. 将本地文件复制到克隆的仓库中
5. 提交并推送更改

## 方案 4：手动上传到 GitHub

1. 进入 GitHub 仓库页面：https://github.com/Mengzhao-Zhi/Loveofmegnzhao
2. 点击 "Add file" → "Upload files"
3. 拖拽或选择您的网站文件（index.html, styles.css, script.js）
4. 填写提交信息并点击 "Commit changes"

## 启用 GitHub Pages

无论使用哪种方案，部署完成后都需要启用 GitHub Pages：

1. 进入 GitHub 仓库页面
2. 点击 "Settings" → "Pages"
3. 选择分支为 "main"，目录为 "/ (root)"
4. 点击 "Save"
5. 等待几分钟，您的网站将发布在：https://mengzhao-zhi.github.io/Loveofmegnzhao/
