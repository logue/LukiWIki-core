# LukiWiki記法

LukiWiki記法はMarkdownとPukiWikiを足して２で割った記法と考えていいです。

草案

## 見出し

Markdown準拠

```
# 見出し１
## 見出し２
### 見出し３
#### 見出し４
##### 見出し５
```

## リスト項目

レベルの表記の仕方がMarkdown風。ただし識別子の文字はPukiWiki風。

### 番号なし

```
- 項目レベル１
 - 項目レベル２
  - 項目レベル３
* 項目レベル１
 * 項目レベル２
  * 項目レベル３
```

### 番号付き

```
+ 項目レベル１
 + 項目レベル２
  + 項目レベル３
```

### チェックボックス

```
[ ] チェックなしレベル１
 [x] チェックありレベル２
  [-] チェック中間状態レベル３
```

## 定義文

PukiWiki準拠

```
:定義|説明文
```

## 整形済みテキスト

GithubのMarkdown準拠。PukiWikiのスペースやタブを先頭に入れる記法はサポートせず。シンタックスハイライトは、CodeMirrorを使用。オプションには、ハイライトさせたい言語を入れる。空欄時は処理しない。

~~~
```[オプション]
...
```
~~~

## テーブル

PukiWik準拠

```
|見出し |見出し |見出し |h
|セル   |セル   |セル   |
```

## ブロック型引用符

PukiWiki準拠

```
>
 引用
<
```

## 水平線

PukiWiki準拠

-を4つ以上

```
----
```

## リンク

PukiWiki、Markdown両方サポート。自動リンクはしない。

```
[[リンク名>リンク先]]
[リンク名](アドレス)
<アドレス>
```

### 強調

```
* 文字列 *
```

### 太文字

強調と同じ表示だが意味合いは異なる。PukiWiki準拠の書き方。

```
'' 文字列 ''
```

## 強調（斜体）

```
** 文字列 **
```

## 斜体

```
'''文字列'''
```

## 下線

```
___文字列___
```

## 字消し線

```
%%文字列%%
```

## コード

Markdown準拠

```
`コード文`
```

## 文字色、背景色、フォントサイズ、上付き、下付き、

Markdownには仕様なし。PukiWiki準拠。--から始まる色はbootstrapのテーマカラー準拠。サイズの単位はrem

```
COLOR(--blue)
BGCOLOR(--gray)
SIZE(1)
SUP(上付き)
SUB(下付き)
LANG(言語)
ABBR(文字列){文字列の説明}
```

## 画像、動画、オーディオ

Markdown準拠だが、動画、オーディオも貼ることができる。

```
![Alt text](メディアファイル "タイトルテキスト"){id class}
```

一応base64変換されたファイルを埋め込むことも可能。

## ブロック型プラグイン

\#から@に変更になっています。（UMLを埋め込む場合もこれ）

入力は複数行対応のブロック型プラグインと同じです。

```
@プラグイン名(オプション,オプション2...){{
変換対象
}}
```

UMLを例にすると{{}}内のテキストがUML画像に変換されます。

```
@uml(plantuml){{
Bob -> Alice: Hello!
}}

## インライン型プラグイン

PukiWikiと全く同じです。

```
&プラグイン名(オプション){変換対象}
```