---
title: GoogleMeetのチャット履歴を保存するChrome拡張作成
date: 2021-09-14 22:09:50
category: chrome_extension
thumbnail: { thumbnailSrc }
draft: false
---

1 記事書いて満足して一切書いてなかったので、メモ代わりに定期的に書いていきたい。。。

## MeetChatLogger

仕事のミーティング等で Google Meet をたまに使っているが、そこに付属されているチャットが少し不便。使ったことのある人はわかると思うが、メッセージが書かれたときにオンラインな人に配信されてサーバにはいっさい保存されない仕様っぽい。なので部屋に入り直しただけで自分からはメッセージが消失してしまう。

それを手軽に解決するために[MeetChatLogger](https://chrome.google.com/webstore/detail/meetchatlogger/ijhffeahfngojfmkdoleghdbgeebknko?hl=ja&)という chrome 拡張を作成。

meet のチャット履歴を chrome storage に保存して、chrome 拡張のポップアップから確認できるようにしたもの。

## React

今回の拡張のポップアップ部分を React で書くことにしました。環境構築はほぼ[こちら](https://medium.com/litslink/how-to-create-google-chrome-extension-using-react-js-5c9e343323ff)をそのまま実施。特に詰まることなく出来た。

### content script も typescript で

上記のサイトで TypeScript+React でポップアップ箇所を作れると同時に content script 部分も typescript で記述できるように設定を説明してくれてるので助かった。

## chrome.storage

今回チャット履歴を保存する場所として chrome.storage を利用した。すごく簡単に扱えて良い。

- localstorage っぽいもの
- localstorage は 5MB の制限があるが、chrome.storage では local に保存すると制限無しで保存できるみたい
  - 権限に`unlimitedStorage`を加える
- chrome.storage.sync を用いると、同じアカウントでデータを共有できるらしい
  - サイズの制限があるので今回は使わなかった
- content script やポップ側のコードからも chrome.storage.local.get などで簡単に呼べる

## 締め

Chrome の拡張は何個か書いたことがあったが React を使ったのは今回が初めてだった。が、特に障害なく書けるので今度アイデアが湧いたらまた何か作りたい。

コードは以下のリポジトリです。
https://github.com/shu1007/meet-chat-logger
