# Zero-width-character
You can change the text to zero-width spaces or reverse it
InvisiText

把秘密藏进看不见的地方 —— 零宽字符隐写工具。

这是什么

InvisiText 是一个纯前端的文字隐写工具。它把你想隐藏的秘密信息编码为零宽字符（Zero-Width Characters），嵌入到一段普通的载体文字中。别人看到的只是一句平常的话，只有用解码功能才能读出真正隐藏的内容。

- 纯 HTML + CSS + JavaScript，单文件实现，无需后端、无需依赖
- 打开 `index.html` 即可使用，也可以直接部署到 GitHub Pages
- 界面遵循 Material Design 风格，移动端自适应

原理

字符	Unicode	含义	
零宽空格	U+200B	二进制 0	
零宽不连字	U+200C	二进制 1	
零宽连字	U+200D	起止分隔符	

编码时，秘密文本先经 UTF-8 转为字节，再转为二进制位串，每一位映射为一个零宽字符，整体包在两个分隔符之间，插入载体文字第一个字符之后。解码时按相反过程还原。

快速开始

```bash
git clone https://github.com/<你的名字>/InvisiText.git
cd InvisiText
# 直接用浏览器打开
open index.html
```

部署到 GitHub Pages

仓库 Settings → Pages → Source 选择 `main` 分支根目录，稍等片刻即可通过 `https://<你的名字>.github.io/InvisiText/` 访问。

使用示例

1. 在「编码」区输入载体文字：`今晚一起吃饭吗`
2. 输入秘密信息：`老地方见`
3. 点击「生成隐写文本」，复制结果发给朋友
4. 朋友在「解码」区粘贴这段文字，点击「解码」即可看到 `老地方见`

注意事项

- 部分平台（某些聊天软件、论坛）会过滤零宽字符，导致密文丢失，使用前请先测试
- 本工具仅供娱乐与技术学习，请勿用于任何违法违规用途

贡献

欢迎提交 Issue 和 Pull Request，详见 [CONTRIBUTING.md](CONTRIBUTING.md)。

许可证

[MIT](LICENSE)
