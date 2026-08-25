
# 个人求职简历模板（XeLaTeX）

> 本仓库存放计算机方向求职简历 LaTeX 源代码
> 参考 https://github.com/io-wy/resume_io-wy 和 https://github.com/LeyuDame/BNUCV.git
> 使用 **XeLaTeX** 编译器，ctexart 中文文档类；支持右上角头像、FontAwesome 图标、自定义主题色。
> 适配岗位：前端 / 全栈 / Java后端 / 运维开发。

## 📁 仓库结构
```

resume/
├── resume.tex          # 简历主源文件
├── Font/               # 字体文件夹，.gitignore 忽略，**不提交到 git**
├── img/
│   └── avatar.png      # 个人头像，tikz 渲染在页面右上角
├── resume.pdf          # 编译输出 PDF
├── .gitignore          # 忽略字体、编译中间产物、PDF 临时文件
└── README.md

```

## ✨ 模板特性
- A4 纸张，紧凑页边距，面向单页简历；
- Tikz 实现右上角头像，页面底部增加页脚邮箱；
- FontAwesome 图标作为章节标题图标；
- 自定义主题蓝色 `#0849A3`；
- 完整模块：个人信息｜教育背景｜学术成果｜获奖证书｜实习经历｜项目经历｜技能特长；
- 支持填写中共党员、SCI论文、算法竞赛、工程实习、RAG大模型项目；
- 中文：方正兰亭黑 Pro；西文：Helvetica Neue LT Pro。

## ⚠️ 字体版权说明（重要）
`Font/` 目录存放**商业付费字体**：方正兰亭黑 Pro、Helvetica Neue LT Pro，受版权保护，**禁止上传到Git仓库**。

克隆仓库后，自行将以下 otf 字体放入 `Font/` 文件夹：
```

Font/
├── ProGB18030.otf              # 方正兰亭黑 Pro 常规
├── ProGB18030 DemiBold.otf     # 方正兰亭黑 Pro 粗体
├── HelveticaNeueLTPro-Roman.otf
└── HelveticaNeueLTPro-Md.otf

```

不想使用商业字体：修改 tex 文件，替换为思源黑体 / Noto Sans CJK 等免费开源字体。

## 🔨 编译方式
### 环境依赖
安装完整 TeXLive / MiKTeX，**必须使用 XeLaTeX**。
> 使用 tikz 定位头像，需要编译 2‑3 次，图片位置才会渲染正确。

本地编译命令（Git Bash / WSL）
```bash
xelatex resume.tex
xelatex resume.tex
xelatex resume.tex
```

VS‑Code + LaTeX‑Workshop：将默认编译器设置为 `xelatex`。

## 📝 使用说明

1. 克隆仓库；
2. 将字体文件放到 `Font/`；
3. 头像图片放置 `img/avatar.png`；不需要头像，直接注释掉全部 tikz 头像代码块；
4. 修改 `resume.tex` 内个人信息、教育背景、实习、项目、学术论文；
5. 多次执行 xelatex，生成 `resume.pdf`。

### Windows Git 常见踩坑

1. pdf、aux、log 等编译产物已在 `.gitignore`，不要提交；
2. **不要用 PDF 阅读器持续打开输出的 pdf**，会产生文件锁，出现 `Permission denied` 权限报错；
3. `.git` 权限报错：关闭占用该目录全部程序，Git Bash 使用管理员身份运行。

## 🏷️ 上游来源

模板版式基于以下开源项目二次开发：

- brucep3/myCV：[https://github.com/brucep3/myCV](https://github.com/brucep3/myCV)
- billryan/resume：[https://github.com/billryan/resume](https://github.com/billryan/resume)

## License

MIT License，可自由 Fork 修改用于个人简历。

> 
> ⚠️ 注意：商业字体不受 MIT 协议覆盖，请自行保证字体版权合规。


配套 `.gitignore` 源码，复制保存为仓库根目录 `.gitignore`：

```gitignore
# LaTeX 编译产物
*.aux
*.log
*.out
*.toc
*.synctex.gz
*.pdf
*.fls
*.fdb_latexmk
