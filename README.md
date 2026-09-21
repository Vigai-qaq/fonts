# fonts

手写体字体文件托管仓库，供微信小程序 `handwrite-miniprogram` 通过 jsDelivr 按需下载。

## 用途

这是一个**小程序项目配套的字体资源仓库**。本仓库只存放本项目所需的字体文件，不用于图片托管、视频分发、文件备份等任何通用文件托管用途。

## 文件

| 文件 | 版本 | 体积 | MD5 |
|---|---|---|---|
| `handwrite-v1.ttf` | v1 | 2.89 MB（3,031,176 字节） | `e7978d63171578c8dda555ab3eb46aeb` |

字体信息：

- 名称：清叶手写体（YiPinQingYeShouXieTi-2）
- 格式：TrueType
- 字形数：6,979（含 6,763 个汉字）
- 字符覆盖：GB2312 全量（一级 + 二级），ASCII 95 个全覆盖
- 嵌入权限：`fsType = 0x8`（可编辑嵌入，允许子集化）
- 版权方：深圳一品信息技术有限公司

## CDN 地址

```text
https://cdn.jsdelivr.net/gh/Vigai-qaq/fonts@v1/handwrite-v1.ttf
```

**请使用 `@v1` 这样的 tag 引用，不要用分支名。** jsDelivr 对精确 tag 的缓存是永久的，
而分支引用只有 12 小时缓存，可能读到不同内容。

本仓库的响应头特性（由 jsDelivr 提供）：

```text
Content-Type: font/ttf
access-control-allow-origin: *
```

这两项正好满足微信小程序 `wx.loadFontFace` 的要求（字体 MIME 类型 + CORS），
使用方无需额外配置。

## 更新字体的正确方式

**不要直接覆盖旧文件**，而要发布新 tag：

```bash
cp 新字体.ttf handwrite-v2.ttf
git add handwrite-v2.ttf
git commit -m "add v2"
git tag v2
git push origin main --tags
```

然后在小程序代码里把地址改成 `@v2/handwrite-v2.ttf` 即可。旧 tag 保持不动，
已发布的地址不会失效。

## 授权说明

本仓库仅存放字体文件的原始副本，**不改变字体的任何授权条款**。
字体版权归深圳一品信息技术有限公司所有，使用前请自行确认授权范围。

`fsType = 0x8` 表示字体的技术嵌入权限为「可编辑嵌入」，
**这不等于授权公开分发**，两者是不同层面的问题。
若有侵权请提 issue，会立即删除。
