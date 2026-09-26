# 弥月Mizuki Q 宠安装与使用教程

按下面的步骤，把「弥月Mizuki」安装到 Codex 桌面端。安装目录统一使用 `mizuki`，宠物显示名称为「弥月Mizuki」，简介为「来自未来的家里蹲兔子博士！」。

![安装后的角色与动作预览](assets/preview.gif)

## 1. 准备应用和安装包

先安装并登录支持自定义宠物的 Codex 桌面端，确认设置中有“宠物”（Pets）入口。还没安装应用时，可参考 [OpenAI 官方入门说明](https://learn.chatgpt.com/docs/quickstart)。

1. 打开 [最新发布页](https://github.com/sssccchao/mizuki-codex-pet/releases/latest)。
2. 在页面的 **Assets** 区域下载 `mizuki-codex-pet.zip`，也可以使用 [安装包直达链接](https://github.com/sssccchao/mizuki-codex-pet/releases/latest/download/mizuki-codex-pet.zip)。
3. Windows 上右键 ZIP，选择“全部解压”；macOS 上双击 ZIP 解压。
4. 打开解压出的 `mizuki-codex-pet` 文件夹，找到 `pet.json` 和 `spritesheet.png`。

本教程的常规安装只需要这两个文件。`spritesheet-v1.png` 用于第 6 节的兼容格式；`assets` 中的 GIF 和单张预览图用于查看效果。

## 2. 将文件放入宠物目录

### Windows

1. 按 `Win + E` 打开文件资源管理器。
2. 点击地址栏，输入 `%USERPROFILE%`，按回车，进入当前用户的文件夹。
3. 打开 `.codex` 文件夹；如果不存在，新建一个名为 `.codex` 的文件夹。
4. 在 `.codex` 内打开或新建 `pets` 文件夹，再在 `pets` 内新建 `mizuki` 文件夹。
5. 从解压的安装包中复制 `pet.json` 和 `spritesheet.png`，粘贴到刚才的 `mizuki` 文件夹。

完整安装路径是：

```text
%USERPROFILE%\.codex\pets\mizuki\
```

例如用户名为 `Alice` 时，目录应当是：

```text
C:\Users\Alice\.codex\pets\mizuki\
├── pet.json
└── spritesheet.png
```

完成后，将 `%USERPROFILE%\.codex\pets\mizuki\` 粘贴到文件资源管理器地址栏，可以直接检查这两个文件。

### macOS

1. 打开“终端”，复制下面的命令并按回车，创建安装目录：

   ```bash
   mkdir -p ~/.codex/pets/mizuki
   ```

2. 打开 Finder，按 `Command + Shift + G`，输入 `~/.codex/pets/mizuki/`，按回车。
3. 将解压得到的 `pet.json` 和 `spritesheet.png` 复制到这个文件夹。

目录应当是：

```text
~/.codex/pets/mizuki/
├── pet.json
└── spritesheet.png
```

两种系统都要让 `pet.json` 直接位于 `mizuki` 文件夹中，与图片并排。不要把解压后的整个项目文件夹再套进 `mizuki`，否则配置会多藏一层。

## 3. 核对配置

安装包中的 `pet.json` 已经配置好，可以直接使用。若需要排查文件内容，用文本编辑器打开它，核对如下：

```json
{
  "displayName": "弥月Mizuki",
  "description": "来自未来的家里蹲兔子博士！  ",
  "spriteVersionNumber": 2,
  "spritesheetPath": "spritesheet.png"
}
```

`spritesheetPath` 必须与同一文件夹内的图片文件名一致。常规安装使用版本 `2` 和 `spritesheet.png`；这张透明精灵图的尺寸是 `1536 × 2288`。

Windows 用户可以开启文件资源管理器的“文件扩展名”显示，确认配置叫 `pet.json`，没有被保存成 `pet.json.txt`。

## 4. 选择并显示弥月

1. 打开 Codex 桌面端的设置。
2. 进入“宠物”（Pets），点击“刷新”（Refresh）。
3. 在宠物列表中选择「弥月Mizuki」。
4. 输入 `/pet`，或在应用命令菜单中选择“显示宠物”（Show pet）。

屏幕上出现预览中的弥月，即表示安装成功。选择和显示宠物的操作可参考 [OpenAI 官方宠物说明](https://learn.chatgpt.com/docs/pets)。

如果刚复制文件后列表没有变化，完全退出应用，再重新打开并刷新。

## 5. 日常使用

| 想做的事 | 操作 |
| --- | --- |
| 显示宠物 | 输入 `/pet` 或选择 Show pet |
| 隐藏宠物 | 再次输入 `/pet`，或右键宠物选择 Hide |
| 移动位置 | 拖动宠物到想放的位置 |
| 调整大小 | 在 Settings → Pets → Customize 中调整 Pet size |
| 换回其他宠物 | 在 Settings → Pets 中重新选择 |

上述控制随应用版本可能略有差异，以 [官方宠物说明](https://learn.chatgpt.com/docs/pets) 和实际菜单为准。

## 6. 使用兼容格式

### 旧版桌面端

如果使用的版本只支持版本 1 精灵图：

1. 将安装包里的 `spritesheet-v1.png` 复制到 `mizuki` 文件夹。
2. 打开 `pet.json`，将 `spriteVersionNumber` 改为 `1`，将 `spritesheetPath` 改为 `spritesheet-v1.png`。
3. 保存配置，回到应用刷新并重新选择「弥月Mizuki」。

修改后的配置是：

```json
{
  "displayName": "弥月Mizuki",
  "description": "来自未来的家里蹲兔子博士！  ",
  "spriteVersionNumber": 1,
  "spritesheetPath": "spritesheet-v1.png"
}
```

版本 1 图片的尺寸是 `1536 × 1872`。以后切回版本 2 时，恢复第 3 节的配置，并确认 `spritesheet.png` 仍在同一文件夹内。

### 网页上传入口

如果账号的网页宠物设置提供 Upload pet，选择安装包里的 `spritesheet-v1.png` 上传。它符合 [官方网页上传规格](https://learn.chatgpt.com/docs/pets) 的透明图片尺寸与大小要求。网页上传的宠物显示在支持的网页聊天内，桌面浮窗仍按前面的步骤安装。

## 7. 更新、整理旧安装和卸载

### 更新到新版本

1. 从 [最新发布页](https://github.com/sssccchao/mizuki-codex-pet/releases/latest) 下载并解压新的安装包。
2. 退出 Codex 桌面端，将原来的 `mizuki` 文件夹复制一份作为备份。
3. 将新版 `pet.json` 和 `spritesheet.png` 复制进 `mizuki` 文件夹，替换同名文件。
4. 重新打开应用，刷新宠物列表，再次选择「弥月Mizuki」。

### 已经使用其他文件夹名安装过

退出应用，在 `.codex/pets/` 内找到之前安装弥月的文件夹，将那一份文件夹改名为 `mizuki`，再打开应用刷新并重新选择。避免为同一只宠物保留多份安装目录，以免列表重复。

### 卸载

先隐藏宠物并退出应用，然后删除 `.codex/pets/mizuki/` 文件夹。重新打开应用并刷新宠物列表。

## 8. 常见问题

### 列表里找不到「弥月Mizuki」

依次检查：`pet.json` 是否直接位于 `pets/mizuki/` 下；配置与图片是否放在同一目录；文件名是否准确；是否点击了 Refresh。仍未出现时，重启应用再检查。

### 能选中宠物，但图片没有显示或显示错乱

检查 `spriteVersionNumber` 与图片是否配套：版本 `2` 对应 `spritesheet.png`，版本 `1` 对应 `spritesheet-v1.png`。重新从安装包复制原图，保持原尺寸和透明背景。

### 动画预览正常，桌面宠物却不动

检查系统的“减少动态效果”（Reduced motion）设置；开启该选项时，宠物会使用静态帧。见 [官方动画设置说明](https://learn.chatgpt.com/docs/pets)。

### 设置里没有宠物入口

先更新桌面应用，再确认当前账号或工作区是否提供宠物功能。本教程的桌面浮窗需要使用支持该功能的桌面端；IDE 扩展不提供对应入口。见 [官方支持范围](https://learn.chatgpt.com/docs/pets)。

### 下载失败或 ZIP 没有解压成功

重新打开 [发布页](https://github.com/sssccchao/mizuki-codex-pet/releases/latest)，在 Assets 中下载 `mizuki-codex-pet.zip`，等下载完成后再解压。下载后应能在项目文件夹中找到第 1 节提到的两个安装文件。
