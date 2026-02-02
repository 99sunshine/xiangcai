# 🚀 GitHub Pages 部署指南
# How to Deploy Your Personal Website to GitHub

---

## 📋 准备工作 Prerequisites

你需要的文件 Files you need:
- `index.html` (主页)
- `journey.html` (我的故事页面)
- `profile1.jpg` (头像照片1)
- `profile2.jpg` (头像照片2)
- 其他旅行照片 (如 journey_img1.jpeg 等)

---

## 🔧 第一步：创建 GitHub 账号
## Step 1: Create a GitHub Account

1. 访问 https://github.com
2. 点击 "Sign up" 注册
3. 填写用户名、邮箱、密码
4. 验证邮箱

---

## 📁 第二步：创建新仓库
## Step 2: Create a New Repository

1. 登录 GitHub 后，点击右上角 "+" → "New repository"

2. 填写仓库信息：
   - **Repository name**: `你的用户名.github.io`
     - 例如：如果用户名是 `alicecai`，仓库名就是 `alicecai.github.io`
     - 这样你的网站地址就是 https://alicecai.github.io
   
   - 或者用其他名字如 `personal-website`
     - 网站地址会是 https://用户名.github.io/personal-website

3. 选择 "Public"（公开）

4. ✅ 勾选 "Add a README file"

5. 点击 "Create repository"

---

## 📤 第三步：上传文件
## Step 3: Upload Your Files

### 方法一：通过网页上传（最简单）

1. 在仓库页面，点击 "Add file" → "Upload files"

2. 将以下文件拖拽到上传区域：
   ```
   index.html
   journey.html
   profile1.jpg
   profile2.jpg
   journey_img1.jpeg
   journey_img2.jpeg
   ... (所有图片)
   ```

3. 在下方 "Commit changes" 区域：
   - 填写 "Add website files"
   - 点击 "Commit changes"

### 方法二：使用 GitHub Desktop（推荐）

1. 下载 GitHub Desktop: https://desktop.github.com

2. 登录你的 GitHub 账号

3. Clone 你的仓库到本地

4. 将所有文件复制到本地仓库文件夹

5. 在 GitHub Desktop 中：
   - 填写 commit message
   - 点击 "Commit to main"
   - 点击 "Push origin"

---

## ⚙️ 第四步：启用 GitHub Pages
## Step 4: Enable GitHub Pages

1. 在仓库页面，点击 "Settings"（设置）

2. 左侧菜单找到 "Pages"

3. 在 "Source" 下：
   - Branch: 选择 `main`
   - Folder: 选择 `/ (root)`
   
4. 点击 "Save"

5. 等待 1-2 分钟，页面会显示：
   ```
   ✓ Your site is live at https://你的用户名.github.io
   ```

---

## 🖼️ 第五步：添加/更换照片
## Step 5: Adding or Changing Photos

### 添加新照片：

1. 在仓库页面点击 "Add file" → "Upload files"

2. 上传新照片

3. **重要**：确保文件名和 HTML 中引用的一致
   ```html
   <!-- index.html 中 -->
   <img src="profile1.jpg" alt="Alice Cai">
   
   <!-- 所以上传的照片必须命名为 profile1.jpg -->
   ```

### 更换照片：

1. 准备新照片，命名为相同的文件名（如 `profile1.jpg`）

2. 上传时选择 "Overwrite" 覆盖

### 照片命名规范：
- 使用英文，不要中文
- 不要有空格，用下划线代替
- 使用小写字母
- 示例：`journey_img1.jpeg`, `profile_photo.jpg`

---

## 📧 第六步：设置联系表单
## Step 6: Contact Form Setup

表单目前配置使用 Formspree 服务。你需要设置自己的 Formspree 账号：

### 设置步骤：

1. 访问 https://formspree.io

2. 点击 "Get Started" 注册（可用 Google/GitHub 登录）

3. 创建新表单：
   - 点击 "New Form"
   - 输入表单名称（如 "Website Contact"）
   - 输入接收邮箱：`caixiang2003@gmail.com`

4. 获取表单 endpoint，格式如：
   ```
   https://formspree.io/f/xxxxxxxx
   ```

5. 在 `index.html` 中找到并替换：
   ```html
   <form action="https://formspree.io/f/xyzevwbk" method="POST">
   ```
   将 `xyzevwbk` 替换为你的表单 ID

---

## 💬 第七步：评论功能说明
## Step 7: Comments Feature

当前评论功能使用 localStorage（浏览器本地存储），这意味着：
- 每个访客只能看到自己设备上的评论
- 评论不会在不同用户之间共享

### 如需真正的跨用户评论系统，推荐：

**选项 1: Giscus（免费，推荐）**
基于 GitHub Discussions，完美配合 GitHub Pages

1. 访问 https://giscus.app
2. 填写你的仓库信息
3. 复制生成的脚本
4. 替换 `index.html` 中的 comments-section

**选项 2: Disqus（免费）**
1. 访问 https://disqus.com
2. 注册并创建站点
3. 获取嵌入代码

---

## 🔗 第八步：添加自定义域名（可选）
## Step 8: Custom Domain (Optional)

如果你有自己的域名（如 alicecai.com）：

1. 在 GitHub 仓库 Settings → Pages

2. 在 "Custom domain" 输入你的域名

3. 在你的域名提供商处添加 DNS 记录：
   ```
   Type: CNAME
   Name: www
   Value: 你的用户名.github.io
   ```

4. 等待 DNS 生效（最多 24 小时）

5. ✅ 勾选 "Enforce HTTPS"

---

## 📝 常见问题 FAQ

### Q: 网站显示 404？
A: 
- 确保有 `index.html` 文件在根目录
- 检查 GitHub Pages 是否已启用
- 等待几分钟让部署完成

### Q: 图片不显示？
A:
- 检查文件名大小写是否匹配（Linux 区分大小写）
- 确保图片已上传到仓库根目录
- 路径应该是 `src="profile1.jpg"` 而不是 `src="./images/profile1.jpg"`

### Q: 如何更新网站？
A:
- 直接在 GitHub 上编辑文件，或上传新文件覆盖
- 更改会在 1-2 分钟内自动生效

### Q: 表单不工作？
A:
- 确保已在 Formspree 设置了自己的表单
- 检查表单 ID 是否正确
- 在 Formspree 后台查看提交记录

### Q: 地图不显示？
A:
- 地图使用 Leaflet.js，需要网络连接
- 检查浏览器控制台是否有错误

---

## 📂 最终文件结构 Final File Structure

```
你的用户名.github.io/
├── index.html          ← 主页（必需）
├── journey.html        ← 我的故事页面（必需）
├── profile1.jpg        ← 头像照片（必需）
├── profile2.jpg        ← 第二张照片（必需）
├── journey_img1.jpeg   ← 旅行照片
├── journey_img2.jpeg
├── journey_img3.png
├── journey_img4.jpeg
├── journey_img5.jpeg
├── journey_img6.jpeg
├── journey_img7.jpeg
├── journey_img8.jpeg
├── journey_img9.jpeg
├── journey_img10.jpeg
├── journey_img11.jpeg
├── journey_img12.jpeg
├── journey_img13.jpeg
├── journey_img14.png
└── README.md           ← 可选，仓库说明
```

---

## ✅ 部署检查清单 Deployment Checklist

- [ ] GitHub 账号已创建
- [ ] 仓库已创建（命名为 `用户名.github.io`）
- [ ] index.html 已上传
- [ ] journey.html 已上传  
- [ ] profile1.jpg 已上传
- [ ] profile2.jpg 已上传
- [ ] 所有 journey 图片已上传
- [ ] GitHub Pages 已启用（Settings → Pages）
- [ ] 网站可以正常访问
- [ ] Formspree 表单已配置
- [ ] 联系表单测试通过
- [ ] 中英文切换正常
- [ ] 互动地图显示正常
- [ ] 书籍章节可展开/收起

---

## 🎉 完成！Congratulations!

你的网站现在应该可以在以下地址访问：

**https://你的用户名.github.io**

### 下一步建议：
1. 分享链接给朋友测试
2. 在简历/名片上添加网站链接
3. 定期更新内容
4. 考虑添加 Google Analytics 追踪访问量

如有问题，可查看：
- GitHub Pages 文档：https://docs.github.com/en/pages
- 仓库 Actions 标签查看部署状态

祝贺你拥有了自己的个人网站！🎊
