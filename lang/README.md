# 语言文件

本目录下的语言文件原本以 Git 子模块形式引用自
[win12-online/win12-locales](https://github.com/win12-online/win12-locales)。

为了让项目能在 Cloudflare（Workers / Pages）上直接部署，此处已将子模块内容
**内联为普通文件**。原因是托管平台在构建时不一定会递归初始化 Git 子模块，
一旦未初始化，`lang/lang/` 会是空目录，`desktop.js` 中的 i18n 加载
（`path: 'lang/lang/'`）就会失败，导致界面文案全部回退。

对应上游提交：`f74bd77f144db7e6693d3cc3046fc06c47107480`

## 许可证

这些文件遵循 **CC0 1.0 Universal**，详见同目录下的 `LICENSE`，
译者名单见 `TRANSLATORS`。

## 如何同步上游更新

```bash
git clone --depth 1 https://github.com/win12-online/win12-locales.git /tmp/win12-locales
cp /tmp/win12-locales/lang/*.properties lang/lang/
cp /tmp/win12-locales/LICENSE  lang/LICENSE
cp /tmp/win12-locales/TRANSLATORS lang/TRANSLATORS
```
