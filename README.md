# 成语拼图（Idiom Puzzle）

一个纯前端、零依赖的 HTML5 成语益智小游戏，单文件即可运行。
本仓库用于托管到 **GitHub Pages**，作为 CrazyGames 开发者资质审核的作品集证明。

## 玩法
- 从打乱的汉字拼出正确成语
- 支持语音朗读、关卡进度本地保存
- 纯 DOM + 原生 JS，无外部 CDN、无第三方依赖

## 技术说明
- 单文件 `index.html`，CSS/JS 全部内联
- 图片内嵌（base64 WebP + 代码生成 SVG），无外部图片请求
- 无任何 `wx.*` 微信接口，普通浏览器直接可玩
- 体积约 164K，远低于平台体积上限

## 本地预览
直接用浏览器打开 `index.html` 即可，无需服务器。

## 从零开始的完整部署流程（GitHub 新用户）

### 第 0 步：注册 GitHub 账号（免费）
1. 打开 https://github.com ，点右上角 **Sign up**
2. 依次填写：**邮箱**、**密码**（至少 15 位或含数字字母）、**用户名**（一旦想好较难改，建议用英文名/拼音）
3. 完成人机验证（拼图）
4. **验证邮箱**：GitHub 会发一封邮件，点里面的 **Verify email address** 链接（不验证无法建仓库/推送）
5. 进入后可选跳过其余引导

### 第 1 步：新建仓库
1. 右上角头像旁点 **+ → New repository**
2. Repository name 填 `idiom-puzzle`
3. 可见性选 **Public**
4. **不要**勾选 "Add a README file" / 任何 Initialize 选项（本地已有完整提交）
5. 点 **Create repository**

### 第 2 步：配置本地推送认证（三选一）
GitHub 已禁用密码登录，推送必须用以下任一方式：
- **方式 A（Windows 推荐，最简单）**：已装 Git for Windows 自带 Git Credential Manager。直接执行第 3 步的 `git push`，会**自动弹出浏览器让你登录 GitHub**，登录后即记住凭证。
- **方式 B（Personal Access Token）**：GitHub 网页 → 头像 → `Settings → Developer settings → Personal access tokens → Tokens (classic) → Generate new token`，勾选 `repo` 权限，生成后**复制保存**（只显示一次）。`git push` 时用户名填 GitHub 用户名，密码框**粘贴这个 token**。
- **方式 C（GitHub CLI）**：终端先 `gh auth login` 按提示登录，再 `git push`。

### 第 3 步：本地推送
在 Git Bash / 终端执行（把 `你的用户名` 换成第 0 步注册的用户名）：
```bash
cd "C:\Users\10955\WorkBuddy\2026-07-25-22-04-47\idiom-puzzle"
git remote add origin https://github.com/你的用户名/idiom-puzzle.git
git branch -M main
git push -u origin main
```

### 第 4 步：开启 GitHub Pages
1. 进入仓库页面 → **Settings → Pages**
2. Source 选 **`main` 分支**，目录选 **`/`（root）**
3. 点 **Save**
4. 约 1–2 分钟后访问 `https://你的用户名.github.io/idiom-puzzle/`

> 仓库含 `.nojekyll`，已禁用 Jekyll 处理，确保游戏原样托管。

## 部署到 GitHub Pages（速查）
1. 在 GitHub 新建 **Public** 仓库，名称 `idiom-puzzle`
2. 本地执行：
   ```bash
   git remote add origin https://github.com/你的用户名/idiom-puzzle.git
   git branch -M main
   git push -u origin main
   ```
   > 推送需 GitHub 账号认证：密码已不可用，请使用 **Personal Access Token**（Settings → Developer settings → PAT，勾选 `repo` 权限）作为密码，或先 `gh auth login`。
3. 仓库 **Settings → Pages → Source 选 `main` 分支、目录 `/`（root）** → Save
4. 约 1–2 分钟后访问 `https://你的用户名.github.io/idiom-puzzle/`

> 仓库含 `.nojekyll`，已禁用 Jekyll 处理，确保游戏原样托管。

## 提交到 CrazyGames 前的补充
在 `index.html` 的 `<head>` 添加一行（ID 在 developers.crazygames.com/generate-id 生成）：
```html
<meta name="crazygames-game-id" content="你的12位ID">
```
