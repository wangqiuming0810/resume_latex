# 经典蓝 LaTeX 简历模版

图标章节 + 蓝色主题的经典款简历模版，版式来源 [brucep3/myCV](https://github.com/brucep3/myCV)（基于 [billryan/resume](https://github.com/billryan/resume) 修改）。
`resume.tex` 内为占位示例内容，请替换为你的真实信息。

## 版式参数

- 10pt 字号、0.8cm 左右边距
- 主题色 `#003E74`、链接色 `#00AEef`
- 节标题图标：教育 / 实习 / 项目 / 技能 四个 FA 图标

## 编译

```bash
xelatex resume.tex
```

需本机装有 TeX Live（XeLaTeX）。

**⚠️ 字体**：`resume.tex` 使用方正兰亭黑 Pro 与 Helvetica Neue LT Pro 两种**商业字体**，版权原因未随仓库分发，需自行获取后放入 `Font/` 目录：

```
Font/
├── FontAwesome.otf              # FA 4.7 图标字体（免费，SIL OFL，已随仓库）
├── ProGB18030.otf               # 方正兰亭黑 Pro 常规（商业，需自备）
├── ProGB18030-DemiBold.otf      # 方正兰亭黑 Pro 粗体（商业，需自备）
├── HelveticaNeueLTPro-Roman.otf # Helvetica Neue LT Pro（商业，需自备）
└── HelveticaNeueLTPro-Md.otf    # 同上，Medium 字重（商业，需自备）
```

## 文件结构

```
latex-classic/
├── resume.tex                  # 简历主文件（占位示例内容）
├── fontawesome.sty             # FA4 图标包（已补丁：从 Font/ 加载字体）
├── fontawesomesymbols-generic.tex
├── fontawesomesymbols-xeluatex.tex   # 已补丁：\faBriefcase 码位 F0B1→F0F2
├── Font/
│   └── FontAwesome.otf              # 随仓库（免费，SIL OFL）
└── preview.png                      # 示例截图
```

## 自定义

- 姓名 / 电话 / 邮箱 / GitHub：`resume.tex` 顶部联系方式行
- 主题色：改 `\definecolor{CVBlue}{RGB}{0,62,116}`
- 链接色：改 `\definecolor{LinkBlue}{RGB}{0,174,239}`
- 章节增删：按 `\section{\makebox[\widthof{\faGraduationCap}][c]{\color{CVBlue}\faXX}\ 章节名}` 格式复制即可，图标列表见 `fontawesome.sty`（\fa* 命令）
