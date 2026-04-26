# 老公养成计划 · 部署说明

## 文件结构
```
husband-plan/
├── index.html        ← 游戏主页面
├── api/
│   └── chat.js       ← Claude API 后端函数（藏着 API Key）
├── vercel.json       ← Vercel 配置
└── README.md         ← 本文件
```

---

## 部署步骤（10分钟搞定）

### 第一步：上传到 GitHub
1. 去 github.com 注册/登录
2. 点右上角 "+" → "New repository"
3. 仓库名填 `husband-plan`，选 Public，点 Create
4. 把这个文件夹里所有文件拖拽上传

### 第二步：部署到 Vercel
1. 去 vercel.com，用 GitHub 账号登录
2. 点 "Add New Project"
3. 选择刚才的 `husband-plan` 仓库，点 Import
4. 直接点 Deploy（不需要改任何设置）
5. 等 1 分钟，得到网址比如 `husband-plan.vercel.app` ✅

### 第三步：配置 Claude API Key
1. 去 console.anthropic.com 获取你的 API Key
2. 在 Vercel 项目页面，点 Settings → Environment Variables
3. 添加一条：
   - Name:  `ANTHROPIC_API_KEY`
   - Value: `sk-ant-xxxxxxxx（你的Key）`
4. 点 Save，然后点 Deployments → Redeploy

### 完成！
把网址发给她，她输入名字和密码就能玩了 🎉

---

## 常见问题

**Q: 事件生成失败怎么办？**
A: 会自动切换到本地备用事件，游戏不会中断。

**Q: 换手机存档还在吗？**
A: 同一浏览器存在 localStorage，换设备输入相同名字+密码即可读档（实际数据目前还在本地，后续可以升级为真正的云存储）。

**Q: API 费用大概多少？**
A: 每次事件生成大约消耗 0.001 美元，正常玩不会超过 1 美元/月。

**Q: 可以自定义内容吗？**
A: 可以！打开 index.html，搜索以下内容直接修改：
- 婚礼日期：搜索 `2026-05-24`
- 祝福文字：搜索 `写给你的悄悄话`
- 游戏名称：搜索 `老公养成计划`
