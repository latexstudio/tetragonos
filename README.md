[//]: # (tetragonos/readme.md)
[//]: # (20190114)

# tetragonos

`tetragonos` 是一个能标注汉字四角号码的 LaTeX 宏包。tetra 者，四也；gon 者，角也。

## 用法

`\getTG{<string>}`：计算汉字字符串`<string>`中第一个汉字的四角号码（新版，带附笔号码）。

举个栗子，`\getTG{汉}` 与 `\getTG{汉字}` 都会展开成“汉”字的四角号码，即 `37140`。

## 范例

`tetragonos-example.tex` 中示范了 `tetragonos` 宏包与 `glossaries` 宏包的联合应用，该文件收录了一段古文，并为其中出现的所有植物名称建立了首字四角号码索引。事实上，字词索引是四角号码最常出现的地方了。

[//]: # (20190115)

## 杂谈

我一直认为王云五先生的四角号码检字法是一种很好的汉字编码方法——首先，它是形码，一来不受异读和破音的影响，二来形码天然是地域中立的。换言之，四角是文字的编码而不是语言的编码，整个汉字圈都能用，与语言或方言无关。有时写一些方言学的东西，用普通话读音编词汇索引就有点别扭了，用方言读音的话拼音方案又杂乱。初学日本语时，生字生词查电子辞书很困难，日语输入法九成九是音码，剩下百分之一是内码，不会读就不会打，打不出来就查不了怎么读。虽然中文输入法能打一部分字，但是像之前一样，又生硬得让人受不了。后来把日语常用汉字的四角号码找出来，塞进了自己写的中文输入法里，才解决了问题。其次，作为形码，四角号码学习成本低，取码快，重码率也不高。偏旁部首检字法特例太多（难检字表可是自古有之），数笔画慢，五笔或者仓颉又不好学（还受到键盘布局的影响，QWERTY布局虽然常见，但不天然），头两笔笔形的索引也有书在用，取码倒用不了多久，取完之后慢慢找吧。

写这个宏包，可以说是受到了 `xpinyin` 宏包的启发。粗略看了一下它的实现，发现定义几万个宏对 LaTeX 来说只是毛毛雨，根本不影响编译速度。2018 年年底，我给自己的标本收藏搞了本带索引的目录，四角号码的映射是用 C++ 对好之后再喂给 LaTeX 的，花时间不说，实现和流程还缺乏美感。有了 `tetragonos`，实现就简单多了。
