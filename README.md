# Easy Macchiato Blue

A refined **dark** Fcitx5 theme based on [Catppuccin Macchiato Blue](https://github.com/catppuccin/fcitx5).

Free and open source (MIT). Not an official Catppuccin project.

![Easy Macchiato Blue preview](./examples/simple.png)

> **主题 + `classicui.conf` 一起用。**  
> `theme.conf` 负责颜色与边距；**字体、主题名、托盘文字等**在 `~/.config/fcitx5/conf/classicui.conf`。  
> 完整推荐参数见 [`examples/classicui.conf`](./examples/classicui.conf)。

## Preview colours (Macchiato + Blue)

| Role | Colour |
|------|--------|
| Panel (Surface0) | `#363a4f` |
| Highlight (Blue) | `#8aadf4` |
| Text | `#cad3f5` |
| Selected text (Base) | `#24273a` |
| Preedit background (Mantle) | `#1e2030` |

## Changes from upstream

- Clearer preedit contrast (`HighlightBackgroundColor` → Mantle)
- Menu selection uses Blue instead of Pink (matches the blue accent)
- Candidate / content margins tuned so the highlight sits inside the panel
- Slightly smaller candidate index numbers (`LabelTextSizeFactor=90`)
- No theme-level `Font=` — fonts come from `classicui.conf`（推荐 Noto CJK）

## Install

### 1. 安装主题文件

```sh
git clone https://github.com/<your-username>/easy-macchiato-blue.git
mkdir -p ~/.local/share/fcitx5/themes/
cp -r ./easy-macchiato-blue/src/easy-macchiato-blue ~/.local/share/fcitx5/themes/
```

### 2. 修改 classicui.conf（必做）

编辑 `~/.config/fcitx5/conf/classicui.conf`，至少设置主题名；字体建议一并配置。

也可直接参考仓库中的完整片段：

```sh
# 仅作对照，勿盲目整文件覆盖（会丢掉你其他插件相关设置）
less ./easy-macchiato-blue/examples/classicui.conf
```

Debian / Ubuntu 可先安装 Noto CJK：

```sh
sudo apt install fonts-noto-cjk
```

**与本主题配套的关键参数：**

| 配置项 | 推荐值 | 说明 |
|--------|--------|------|
| `Theme` | `easy-macchiato-blue` | 对应 themes 目录名 |
| `DarkTheme` | `easy-macchiato-blue` | 深色主题槽位 |
| `UseDarkTheme` | `False` | 不跟随系统时固定用 `Theme`；若要跟随系统可改 `True` |
| `UseAccentColor` | `False` | 避免系统重点色覆盖 Macchiato Blue |
| `Font` | `"Noto Sans CJK SC 13"` | 候选字体 |
| `MenuFont` | `"Noto Sans CJK SC Medium 11"` | 菜单字体 |
| `TrayFont` | `"Noto Sans CJK SC Bold 12"` | 托盘文字图标字体 |
| `TrayTextColor` | `#f6f5f4` | 托盘文字（深色环境） |
| `TrayOutlineColor` | `#77767b` | 托盘文字描边 |
| `PreferTextIcon` | `True` | 优先文字托盘图标 |
| `ShowLayoutNameInIcon` | `True` | 图标中显示布局名 |
| `UseInputMethodLanguageToDisplayText` | `True` | 按输入法语言显示字形 |
| `Vertical Candidate List` | `False` | 横向候选（与默认边距观感一致） |
| `WheelForPaging` | `True` | 滚轮翻页 |
| `EnableFractionalScale` | `True` | Wayland 分数缩放 |
| `ForceWaylandDPI` | `0` | 不强制覆盖字体 DPI |
| `PerScreenDPI` | `False` | X11 每屏 DPI（一般可关） |

写入示例：

```ini
# 垂直候选列表
Vertical Candidate List=False
# 使用鼠标滚轮翻页
WheelForPaging=True
# 字体
Font="Noto Sans CJK SC 13"
# 菜单字体
MenuFont="Noto Sans CJK SC Medium 11"
# 托盘字体
TrayFont="Noto Sans CJK SC Bold 12"
# 托盘标签轮廓颜色
TrayOutlineColor=#77767b
# 托盘标签文本颜色
TrayTextColor=#f6f5f4
# 优先使用文字图标
PreferTextIcon=True
# 在图标中显示布局名称
ShowLayoutNameInIcon=True
# 使用输入法的语言来显示文字
UseInputMethodLanguageToDisplayText=True
# 主题
Theme=easy-macchiato-blue
# 深色主题
DarkTheme=easy-macchiato-blue
# 跟随系统浅色/深色设置
UseDarkTheme=False
# 当被主题和桌面支持时使用系统的重点色
UseAccentColor=False
# 在 X11 上针对不同屏幕使用单独的 DPI
PerScreenDPI=False
# 固定 Wayland 的字体 DPI
ForceWaylandDPI=0
# 在 Wayland 下启用分数缩放
EnableFractionalScale=True
```

繁体或其他语区可把 `SC` 换成 `TC` / `HK` / `JP` / `KR`（需已安装对应 Noto CJK 字体）。

### 3. 重载

```sh
fcitx5-remote -r
# or: fcitx5 -r
```

也可在 Fcitx5 → Addons → Classic User Interface 中选择 **Easy Macchiato Blue**，但字体等仍建议在 `classicui.conf` 中按上表设置。

## License

[MIT](./LICENSE) — same family as upstream.

- Copyright (c) 2021 Catppuccin  
- Copyright (c) 2026 easy  

See [NOTICE](./NOTICE) for full attribution.

## Credits / Thanks

Upstream project: [catppuccin/fcitx5](https://github.com/catppuccin/fcitx5)

- [justTOBBI](https://github.com/justTOBBI)
- [Isabelincorp](https://github.com/isabelincorp)
- [Kurome](https://github.com/kuromedayo)
- [ayamir](https://github.com/ayamir) (listed in upstream README)

Palette: [Catppuccin](https://catppuccin.com/palette/) — Macchiato flavour, Blue accent.
