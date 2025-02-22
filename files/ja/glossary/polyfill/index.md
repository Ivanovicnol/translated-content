---
title: Polyfill (ポリフィル)
slug: Glossary/Polyfill
tags:
  - Browser Support
  - CodingScripting
  - Glossary
  - JavaScript
  - polyfill
translation_of: Glossary/Polyfill
---
ポリフィルとは、最近の機能をサポートしていない古いブラウザーで、その機能を使えるようにするためのコードです。大抵はウェブ上の JavaScript です。

例えば、ポリフィルを使用して、独自の IE フィルターを使用して IE7 の {{cssxref("text-shadow")}} の機能を模倣したり、 JavaScript を使用して rem の単位やメディアクエリーを模倣して、適切なスタイル付けを動的に調整したり、その他の必要な機能を提供したりすることができます。

ポリフィルのみを使用しない理由は、機能やパフォーマンスをより良くするためです。ネイティブな API の実装は、ポリフィルよりも多くの機能を持ち、高速です。例えば、 [Object.create のポリフィル](/ja/docs/Web/JavaScript/Reference/Global_Objects/Object/create#polyfill)は、 Object.create の非ネイティブな実装で可能な機能のみを含んでいます。

その他にも、ブラウザーが同じ機能を異なる方法で実装している場合の問題に対処するためにポリフィルが使用されることもあります。ポリフィルは、特定のブラウザーの標準外の機能を使って、 JavaScript が標準に準拠した方法でその機能にアクセスするための方法を提供します。今日ではこのような理由でポリフィルを使用することは稀ですが、ブラウザーごとに JavaScript の実装方法が大きく異なっていた IE6 や Netscape の時代には、特に多く見られました。 [JQuery の最初のバージョン](https://ajax.googleapis.com/ajax/libs/jquery/1.12.4/jquery.js)は、ポリフィルの早期の例の一つでした。これは基本的に、 JavaScript 開発者に、すべてのブラウザーで動作する単一の共通 API を提供するために、ブラウザー固有の回避策をまとめたものでした。当時、 JavaScript 開発者は、ウェブサイトをすべての端末で動作させようとすると大きな問題を抱えていました。ブラウザー間の差異が大きく、ユーザーのブラウザーに応じてウェブサイトのプログラムを根本的に変えたり、ユーザーインターフェイスを大きく変えたりしなければならなかったからです。そのため、 JavaScript の開発者が利用できるのは、すべてのブラウザーでほぼ一貫して動作するごく一部の JavaScript API のみでした。現代のブラウザーは、ほとんどが標準的な意味に従って幅広い API を実装しているので、ブラウザー固有の実装を処理するためにポリフィルを使うことは今日ではあまり一般的ではなくなりました。

## 詳細情報

### 一般知識

- [What is a polyfill?](https://remysharp.com/2010/10/08/what-is-a-polyfill) (この単語の創案者である Remy Sharp による記事)
