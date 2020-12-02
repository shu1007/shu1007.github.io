---
title: Gatsbyでブログを作ってみた
date: 2020-12-02 22:12:00
category: react
thumbnail: { thumbnailSrc }
draft: false
---

最近仕事で React について調べていて、React のフレームワークの Gatsby でテンプレートから簡単にブログが作れそうだったので作ってみた。

## Gatsby

[Gatsby](https://www.gatsbyjs.com/)は React のフレームワーク。SSG(Static Site Generators)なので build 時にページを静的に作ってくれます。なので静的サイトのホスティングサービス(github pages、Netlify 等)にデプロイすれば別途サーバーが必要になったりしないのが手軽で良い。

## Starter

Gatsby は Starter と呼ばれてるテンプレートがあってそれを元にプロジェクトが構築できる。
Starter は以下のページで沢山種類が確認できる。ブログからポートフォリオ用のサイトっぽいものまで沢山ある。  
https://www.gatsbyjs.com/starters/

このブログはここから[gatsby-starter-bee](https://www.gatsbyjs.com/starters/JaeYeopHan/gatsby-starter-bee)というのを選んで作ってみた。見た目が POP で 1 記事 1 つだけどカテゴリを決めてトップからカテゴリで絞る機能もあったのでこれにしてみた。

構築は本当に簡単で、以下を叩くだけで選択した Starter でプロジェクトが作成される。あとは自分用に情報を変えて、コンテンツを追加していく感じで正直プログラムの知識もそこまで必要ないくらい簡単。

- gatsby-cli のインストール
- プロジェクトの作成

```sh
npm install -g gatsby-cli

gatsby new <プロジェクト名> https://github.com/JaeYeopHan/gatsby-starter-bee
```
