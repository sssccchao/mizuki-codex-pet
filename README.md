# 弥月Mizuki · 给小博兔的 Q 宠

> 来自未来的家里蹲兔子博士！

把弥月做成了一只像素 Q 版 Codex 宠物，分享给小博兔们。黑兔耳、金色双马尾和粉黑裙装都保留了，还有画面左紫、右粉的异色眼。

![弥月Mizuki 动画预览](assets/preview.gif)

[下载宠物安装包](https://github.com/sssccchao/mizuki-codex-pet/releases/latest/download/mizuki-codex-pet.zip) · [查看发布页](https://github.com/sssccchao/mizuki-codex-pet/releases/latest)

## 安装到 Codex 桌面端

1. 下载上面的 ZIP，解压后找到 `pet.json` 和 `spritesheet.png`。
2. 在 Windows 文件资源管理器地址栏输入 `%USERPROFILE%\.codex\pets\`，新建 `pink-bunny` 文件夹。目录不存在时先创建目录。
3. 将 `pet.json` 和 `spritesheet.png` 放进 `pink-bunny` 文件夹，保持这两个文件名不变。
4. 打开 Codex 设置 → 宠物（Pets）→ 刷新（Refresh），选择「弥月Mizuki」。
5. 输入 `/pet`，或使用“显示宠物”（Show pet）入口。

macOS 使用用户目录下的 `~/.codex/pets/pink-bunny/`，放入同样的两个文件，再刷新宠物列表。

安装后的目录示例：

```text
.codex/
└── pets/
    └── pink-bunny/
        ├── pet.json
        └── spritesheet.png
```

需要应用提供自定义宠物功能。刷新、选择及显示宠物的操作可参考 [OpenAI 官方宠物说明](https://learn.chatgpt.com/docs/pets)。

## 兼容旧版格式

桌面端默认使用版本 2 精灵图。若入口要求 `1536 × 1872` 的透明图，请使用仓库中的 `spritesheet-v1.png`；该尺寸也符合 [官方文档中的网页宠物上传规格](https://learn.chatgpt.com/docs/pets)。

使用旧版桌面格式时，将配置中的 `spriteVersionNumber` 改为 `1`，`spritesheetPath` 改为 `spritesheet-v1.png`，并把兼容图放到配置旁边。

## 文件与动作

| 文件 | 用途 |
| --- | --- |
| `pet.json` | 宠物名称、简介与精灵图配置 |
| `spritesheet.png` | 版本 2，1536 × 2288，8 列 × 11 行 |
| `spritesheet-v1.png` | 版本 1 兼容图，1536 × 1872 |
| `assets/preview.gif` | 动作预览，57 帧，10.08 秒 |
| `assets/portrait.png` | 正面透明预览 |
| `assets/ponytail-comparison.png` | 双马尾修饰前后对比 |
| `docs/` | 图像生成、异色眼修正和头发修饰提示词 |
| `分享动态.md` | 可复制的分享文案 |

动作包括待机、眨眼、左右移动、挥手、跳跃、失落、等待、思考、完成，以及看向不同方向。部分帧会在循环中复用。

每帧 192 × 208，使用 96 × 104 的逻辑像素网格整数放大。精灵图保留透明背景。

## 制作记录

这是弥月的粉丝同人 Q 宠。角色图像使用 Codex 内置图像工具生成，再整理成可安装的宠物精灵图。

本版已校正异色眼，并将双马尾从圆鼓的发团收成弯曲、末端收尖的发束，清理旧发辫周围的残留像素。全部 88 个帧位置通过尺寸、透明度、边距和像素网格检查。

![双马尾修饰前后](assets/ponytail-comparison.png)
