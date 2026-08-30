# 音楽ゲーム学園 ポリシー文書

音楽ゲーム学園のポリシー文書（学園憲章・学園規則・ガイドライン類）のソースリポジトリです。

## 文書の階層

上位の文書に反する下位の文書は、効力を有しません。

```
学園憲章       … 原則
  ↓
学園規則       … 制度
  ↓
ガイドライン類 … 運用（教務主事の手引き ほか）
```

ガイドラインの位置づけ、効力および改正手続は、学園規則第1章第5条に定めがあります。

## 学園憲章の正本

**学園憲章の正本は `academy-charter/` です。**

学園憲章の本文は、次の2箇所に同一の内容で置かれています。

| パス | 位置づけ |
|---|---|
| `academy-charter/ja/academy-charter.tex` | **正本** |
| `academy-regulations/ja/00_01.tex` | 学園規則の冒頭に読者の便宜のため収録した写し |

学園憲章を改正するときは、まず `academy-charter/` を改め、その内容を `academy-regulations/ja/00_01.tex` に反映してください。両者が食い違う場合は、`academy-charter/` の内容が優先します。

なお学園憲章の改正には、憲章第10条に定める投票を含む手続が必要です。

## ディレクトリ構成

```
academy-charter/            学園憲章
  ja/                       日本語版（正本）
  en/                       英語版（将来の国際対応用。現在は空）
  published/                公開済みPDF

academy-regulations/        学園規則
  ja/                       日本語版
  en/                       英語版（将来の国際対応用。現在は空）
  published/                公開済みPDF

guidelines/                 ガイドライン類
  deans-handbook/           教務主事の手引き
    ja/ en/ published/

preamble.tex                3文書共通のLaTeXプリアンブル
```

`en/` は将来の国際対応に備えた枠組みで、現在は意図的に空です。

## ソースの構成

学園規則および教務主事の手引きは、`main.tex` が章ごとのファイルを `\input` する構成です。ファイル名の数字は章番号に対応します（学園規則の `00_01.tex` は章番号を持たない学園憲章）。

## ビルド

LuaLaTeX でコンパイルします。クラスは `jlreq` です。

```
cd academy-regulations/ja
latexmk -lualatex main.tex
```

`published/` 配下のPDFは、公開した版を `<言語>_<文書名>_version-<版数>.pdf` の形式で保存したものです。
