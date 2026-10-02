# 音楽ゲーム学園 ポリシー文書

音楽ゲーム学園のポリシー文書（学園憲章・学園規則・ガイドライン類）のソースリポジトリです。以下の改訂案は、リポジトリの編集だけでは制定・改正・施行・公示されません。

## 正本・参考訳と版

**英語版は参考訳です。内容に相違がある場合は日本語版を優先します。** 日本語の改訂案も、必要な手続と公示が終わるまでは現行版に代わりません。`published/` は過去に公開した PDF を保存し、作業中のソースを公開版として扱いません。

| 文書 | 日本語のソース・状態 | 英語の参考訳 | 版・更新日 |
|---|---|---|---|
| 学園憲章 | `academy-charter/ja/academy-charter.tex` 正本、変更なし | `academy-charter/en/main.md` | 日本語公開版 1、文書日付 2026-08-07／参考訳 1.0、2026-09-27 |
| 学園規則 | `academy-regulations/ja/` 改訂案。公開済み版 2 は `published/` | `academy-regulations/en/main.md` | 改訂案 0.1、2026-09-27／英訳案 0.1、2026-09-27 |
| 教務主事の手引き | `guidelines/deans-handbook/ja/` 改訂案。公開済み版 2 は `published/` | `guidelines/deans-handbook/en/main.md` | 改訂案 0.1、2026-09-27／英訳案 0.1、2026-09-27 |
| 学生の手引き | `guidelines/students-handbook/ja/main.md` 未制定案 | `guidelines/students-handbook/en/main.md` | 案 0.1、2026-09-27 |
| 講師向け運用案内 | `guidelines/instructors-guide/ja/main.md` 旧ガイドラインの改訂案・日本語ソース | `guidelines/instructors-guide/en/main.md` | 案 0.1、2026-09-27 |

訳語は [`terminology.md`](terminology.md) にまとめています。募集人数の制度案と履修記録の実務案は `proposals/` にあり、施行文書ではありません。

Discord のコミュニティルールと公式掲示板は公示済みです。作業用の Discord 設定エクスポートには投稿本文がなく、共有されたコミュニティルール以外の記事本文は未確認です。新たな案内を公示する前に現行の投稿本文と照合してください。

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
  en/                       英語の参考訳
  published/                公開済みPDF

academy-regulations/        学園規則
  ja/                       日本語版
  en/                       英語の参考訳
  published/                公開済みPDF

guidelines/                 ガイドライン類
  deans-handbook/           教務主事の手引き
    ja/ en/ published/
  students-handbook/        学生の手引き（案）
    ja/ en/
  instructors-guide/        講師向け運用案内（案）
    ja/ en/

proposals/                  制度・実務の未決定案
terminology.md              日英用語表

preamble.tex                3文書共通のLaTeXプリアンブル
```

`en/` の文書はすべて参考訳です。日本語の改訂案と英訳案を照合してから公示対象を決めてください。

## ソースの構成

学園規則および教務主事の手引きは、`main.tex` が章ごとのファイルを `\input` する構成です。ファイル名の数字は章番号に対応します（学園規則の `00_01.tex` は章番号を持たない学園憲章）。

## ビルド

LuaLaTeX でコンパイルします。クラスは `jlreq` です。

```
cd academy-regulations/ja
latexmk -lualatex main.tex
```

`published/` 配下のPDFは公開済み版の保存です。今回のビルド成果物を置く場所ではありません。規則の改正には第9章の発議・事前通知・学園長による公示、憲章の改正には憲章第10条の手続が必要です。学生の活動に関わるガイドラインの制定・改正・廃止は規則第1章第5条に従って公示します。
