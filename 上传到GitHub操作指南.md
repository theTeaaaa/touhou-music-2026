# 上传到 GitHub 操作指南

你已经安装好了 Git，文件也已经在这个目录里准备完毕。接下来的步骤有两种方式，选一种即可。

---

## 方式一：通过网页上传（最简单，不需要额外操作）

适合偶尔上传、不想配置命令行。封面图片较多（20 张），网页上传可能需要逐个拖入，操作略繁琐。

1. 打开 GitHub 官网 https://github.com 并登录（没有账号先注册）。
2. 点击右上角 **+** → **New repository**（新建仓库）。
3. 仓库名称填 `touhou-music-2026`（或自己喜欢的中文/英文名）。
4. 可见性建议选 **Public**（公开）或 **Private**（只有自己可见）。
5. 其他选项保持默认，点击 **Create repository**。
6. 进入仓库后点击 **Uploading an existing file**（上传已有文件）。
7. 打开文件夹 `C:\Users\STELLE\Documents\Codex\2026-08-26\bnag\outputs\`，把里面的文件全部拖入网页上传区（包括 `covers` 文件夹）。
8. 页面下方填写提交说明（例如 `首次上传`），点击绿色 **Commit changes** 按钮。

完成！访问 `https://你的用户名.github.io/仓库名/` 即可在线浏览（需在仓库 Settings → Pages 中开启）。

---

## 方式二：使用 GitHub Desktop 图形客户端（推荐）

适合以后还想继续更新网页的人，不用碰命令行。

1. 下载并安装 GitHub Desktop：https://desktop.github.com
2. 打开 GitHub Desktop，登录你的 GitHub 账号。
3. 点击 **File** → **Add local repository**（添加本地仓库）。
4. 路径选择 `C:\Users\STELLE\Documents\Codex\2026-08-26\bnag\outputs\`。
5. 软件会识别到已初始化的 Git 仓库，点击 **Publish repository**（发布仓库）。
6. 填写仓库名称，选择公开/私有，点击发布。

以后每次修改文件，只需在 GitHub Desktop 里填写说明、点击 **Commit**，再点击 **Push** 上传即可。

---

## 方式三：使用命令行（适合熟悉终端的人）

### 第一步：设置身份（只需做一次）

打开 PowerShell，依次运行：

```powershell
git config --global user.name "你的GitHub用户名"
git config --global user.email "你的GitHub邮箱"
```

### 第二步：提交文件

```powershell
cd "C:\Users\STELLE\Documents\Codex\2026-08-26\bnag\outputs"
git commit -m "上传 2026 东方project 音乐专辑一览"
```

### 第三步：在 GitHub 创建远程仓库并关联

1. 按方式一的 2–5 步在 GitHub 网页上新建一个空仓库。
2. 仓库创建成功后，复制它的地址（形如 `https://github.com/用户名/仓库名.git`）。
3. 在 PowerShell 中运行：

```powershell
git remote add origin 你的仓库地址
git push -u origin main
```

首次推送时，浏览器会弹出 GitHub 登录窗口，登录并授权即可。

---

## 开启 GitHub Pages（让网页可以被直接访问）

上传成功后：

1. 进入仓库页面 → **Settings** → **Pages**。
2. 在 **Source** 处选择 `Deploy from a branch`。
3. 分支选 `main`，目录选 `/ (root)`，点击 **Save**。
4. 等待约 1 分钟，访问 `https://你的用户名.github.io/仓库名/` 即可看到网页。

本目录已包含 `index.html`，GitHub Pages 会自动将其作为首页；它会跳转到中文文件名的正式页面。
