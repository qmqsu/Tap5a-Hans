# Tap5a 简体中文汉化版 · Final Cut Pro 插件 / 模板

> **非官方汉化。** 本仓库是 [Tap5a](http://bit.ly/2oGLAoH) 系列**免费** Final Cut Pro 插件的简体中文汉化版，
> 汉化了**检查器参数名**与**模板显示名**，方便中文用户使用。
> 原插件作者：**Tapio Haaja（tap5a）**，版权归原作者所有。

---

## 目录

- [包含内容](#包含内容)
- [汉化说明](#汉化说明)
- [安装方法](#安装方法)
- [卸载方法](#卸载方法)
- [常见问题](#常见问题)
- [支持原作者](#支持原作者)
- [免责声明](#免责声明)

---

## 包含内容

### 效果 Effects（4 个）

| 原名称 | 中文显示名 |
| --- | --- |
| Tap5a Quick In-Out Animator | Tap5a 快速进出动画器 |
| Tap5a Quick In-Out Bouncer | Tap5a 快速进出弹跳 |
| Tap5a Quick In-Out Revealer | Tap5a 快速进出显现器 |
| Tap5a Zoom Highlight | Tap5a 缩放高亮 |

### 标题 Titles（4 个）

| 原名称 | 中文显示名 |
| --- | --- |
| Tap5a Autosize Text Background | Tap5a 自适应文字背景 |
| Tap5a Multiline Text Backgr. 2 | Tap5a 多行文字背景 2 |
| Tap5a Multiline Text Background | Tap5a 多行文字背景 |
| Tap5a Simple Text Revealer | Tap5a 简单文字显现 |

---

## 汉化说明

本次汉化包含两个层次：

1. **参数名汉化（333 处）**
   直接修改 `.moef` / `.moti` 文件内部的参数标签 —— 即 `<target>`（检查器参数名）、`<entry>`（下拉选项名）、`<group>`（分组名）三类标签的 `name` 属性。
   仅改这三类标签，不触碰 `object`（id）、`channel`（数字路径）等引用字段，因此**不影响模板内部引用**。

2. **模板显示名汉化**
   采用 macOS 原生的 `.localized` 机制：
   - 在模板文件夹名后追加 `.localized` 后缀；
   - 在该文件夹内写入 `.localized/zh_CN.strings`（XML plist，键为原名、值为中文名）。
   Final Cut Pro 读取时会自动剥离 `.localized` 后缀，因此**文件夹名仍等于模板文件名，引用不会断链**。
   这是 Apple 自家模板（如 `Comic Looks.localized` → 「漫画效果」）使用的同款机制。

> 说明：文件夹名后的 `.localized` 是**显示名机制**，不是文件损坏。请勿手动去掉该后缀，否则中文显示名会失效。

---

## 安装方法

### 方式一：手动复制（推荐）

1. 下载本仓库（`Code` → `Download ZIP`，或用 `git clone`）。
2. 打开 Finder，前往 `~/Movies/Motion Templates/`（若不存在请先手动创建）。
3. 将本仓库 `Effects/` 下的 **4 个 `.localized` 文件夹**复制到：
   ```
   ~/Movies/Motion Templates/Effects/Tap5a/
   ```
   （`Tap5a` 文件夹不存在则新建。）
4. 将本仓库 `Titles/` 下的 **4 个 `.localized` 文件夹**复制到：
   ```
   ~/Movies/Motion Templates/Titles/Tap5a/
   ```
5. **完全退出并重启 Final Cut Pro**。
6. 在 FCP 的「效果浏览器」中，找到 **Effects → Tap5a** 与 **Titles → Tap5a** 分类即可看到中文名。

### 方式二：命令行一键安装

在仓库根目录执行：

```bash
# 效果
mkdir -p ~/Movies/"Motion Templates"/Effects/Tap5a
cp -R Effects/*.localized ~/Movies/"Motion Templates"/Effects/Tap5a/

# 标题
mkdir -p ~/Movies/"Motion Templates"/Titles/Tap5a
cp -R Titles/*.localized ~/Movies/"Motion Templates"/Titles/Tap5a/
```

然后重启 Final Cut Pro。

---

## 卸载方法

删除对应目录即可：

```bash
rm -rf ~/Movies/"Motion Templates"/Effects/Tap5a
rm -rf ~/Movies/"Motion Templates"/Titles/Tap5a
```

如需**只删除个别模板**，进入对应 `Tap5a` 文件夹删除该模板的 `.localized` 文件夹即可。

> 若你之前安装过英文原版，建议先删除旧文件夹，再复制本汉化版，避免重名冲突。

---

## 常见问题

**Q：安装后 FCP 里还是显示英文名？**
A：请确认三点 —— ① 系统语言为「简体中文」；② 文件夹名保留了 `.localized` 后缀；③ 已**完全重启** Final Cut Pro（FCP 只在启动时扫描模板）。

**Q：效果浏览器里找不到 Tap5a 分类？**
A：检查是否复制到了正确的分类目录（Effects 对应 `Effects/Tap5a/`，Titles 对应 `Titles/Tap5a/`），并确认文件夹名没有被系统改动。

**Q：会影响我已有的工程吗？**
A：不会。参数名汉化只改显示文本，`object` / `channel` 引用未动；显示名机制是系统级的，不影响模板内部结构。

**Q：支持哪些 FCP 版本？**
A：这些模板基于 Motion 模板格式，适用于 Final Cut Pro 10.4 及以上。原插件较早期，新版 FCP 一般可正常使用。

---

## 支持原作者

这些插件是 **Tapio Haaja（tap5a）** 多年利用业余时间免费制作的。
如果你觉得好用，请通过以下方式支持他：

- 全部免费插件合集：<http://bit.ly/2oGLAoH>
- 捐赠（PayPal）：<https://paypal.me/tap5a>
- YouTube：<http://bit.ly/tilaatap5a>
- X / Instagram：[@tap5a](https://twitter.com/tap5a)
- LinkedIn：<https://www.linkedin.com/in/tapiohaaja>

---

## 免责声明

- 本仓库为**第三方非官方汉化**，与原插件作者 Tapio Haaja 无隶属关系，也**未获得其明示授权**。
- 插件本体（`.moef` / `.moti`、图标等）版权归 **Tapio Haaja** 所有；本仓库仅提供**中文翻译文本**的便利性修改。
- 若原作者对本仓库的再分发有异议，请[提 Issue](../../issues) 或联系维护者，我们会**立即下架**。
- 请勿将本仓库用于商业售卖。请优先从[作者官方渠道](http://bit.ly/2oGLAoH)下载原版并支持作者。
