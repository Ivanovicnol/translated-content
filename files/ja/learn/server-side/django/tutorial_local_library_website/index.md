---
title: 'Django チュートリアル: 地域図書館ウェブサイト'
slug: Learn/Server-side/Django/Tutorial_local_library_website
tags:
  - Python
  - django
  - チュートリアル
  - 初心者
translation_of: Learn/Server-side/Django/Tutorial_local_library_website
---
{{LearnSidebar}}{{PreviousMenuNext("Learn/Server-side/Django/development_environment", "Learn/Server-side/Django/skeleton_website", "Learn/Server-side/Django")}}

実践的なチュートリアルシリーズの最初の記事は、学習する内容を説明し、後の記事で進めていく「地域図書館」のサンプルウェブサイトの概要を示しています。

| 前提条件: | [Django の紹介](/ja/docs/Learn/Server-side/Django/Introduction)を読んでください。以下の記事では、[Django 開発環境をセットアップする](/ja/docs/Learn/Server-side/Django/development_environment)必要があります。 |
| --------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 目的:     | このチュートリアルで使用されているサンプルアプリケーションを紹介し、読者が何をするかを理解できるようにします。                                                                                                  |

## 概要

MDN "地域図書館" Django チュートリアルへようこそ。ここでは、地域図書館のカタログを管理するための Web サイトを開発します。

この一連のチュートリアルの記事でやることは次の通りです:

- Django のツールを使用して、Web サイトのスケルトンとアプリケーションを作成します。
- 開発用サーバーを起動および停止します。
- アプリケーションのデータを表すモデルを作成します。
- Django 管理サイトを使用してサイトのデータを設定します。
- さまざまな要求に応じて特定のデータを取得するためのビューを作成し、ブラウザーに表示する HTML として、データをレンダリングするためのテンプレートを作成します。
- 異なる URL パターンを特定のビューに関連付けるためのマッパーを作成します。
- ユーザーの認可とセッションを追加して、サイトの動作とアクセスを制御します。
- フォームを使います。
- アプリケーションのテストコードを書きます。
- Django のセキュリティを効果的に使用します。
- アプリケーションを本番環境にデプロイします。

これらの話題のいくつかについて学び、他の話題にも簡単に触れました。チュートリアルシリーズの最後は、あなた自身で簡単な Django アプリケーションを開発するのに十分な知識が必要です。

## 地域図書館ウェブサイト

_地域図書館（LocalLibrary）は、この一連のチュートリアルの過程で作成および展開する Web サイトの名前です。ご存じのように、ウェブサイトの目的は、利用可能な書籍を閲覧してアカウントを管理できる小さな地域図書館のオンラインカタログを提供することです。_

この例は慎重に選択されています。なぜなら、必要に応じて細かく表示することができ、ほぼすべての Django 機能を表示するために使用できます。 さらに重要なことは、Django Web フレームワークの最も重要な機能をガイドする方法を提供できることです:

- 最初のいくつかのチュートリアルの記事では、図書館員が利用可能な書籍を見つけるために使用できる簡単なブラウズ専用図書館を定義します。これにより、ほぼすべての Web サイトに共通する操作、つまりデータベースからの内容の読み取りと表示を探ります。
- 進めていくと、図書館の例は、より高度な Django の機能を説明するために自然に拡張していきます。たとえば、ユーザーが書籍を予約できるように図書館を拡張し、これを使ってフォームの使用方法をデモし、ユーザー認証をサポートできます。

これは非常に拡張可能な例ですが、地域図書館と呼んでいます。理由は、Django をすぐに起動して実行するのに役立つ最小限の情報を表示したいと考えているからです。つまり、書籍、本のコピー、作者関する情報、およびその他の重要な情報は保存します。しかし、図書館が保管する可能性のある他のアイテムに関する情報を保管したり、複数の図書館サイトやその他の「大きな図書館」機能をサポートするために必要なインフラストラクチャーを提供することはありません。

## 詰まってます、どこでソースを入手できますか？

チュートリアルを進めるうちに、各ポイントでコピー＆ペーストするための適切なコードスニペットが提供されます。また、この他に自分で拡張してほしいコードもあります（いくつかのガイダンスがあります）。

詰まった場合は、ウェブサイトの完全に開発されたバージョンを[Github 上](https://github.com/mdn/django-locallibrary-tutorial)で見ることができます。

## 要約

地域図書館ウェブサイトについてと、何を学ぶのかをもう少し知りました。今度は例を含む[スケルトンプロジェクト](/ja/docs/Learn/Server-side/Django/skeleton_website)を作成しましょう。

{{PreviousMenuNext("Learn/Server-side/Django/development_environment", "Learn/Server-side/Django/skeleton_website", "Learn/Server-side/Django")}}

## このモジュール内

- [Django の紹介](/ja/docs/Learn/Server-side/Django/Introduction)
- [Django 開発環境の設定](/ja/docs/Learn/Server-side/Django/development_environment)
- [Django チュートリアル: 地域図書館ウェブサイト](/ja/docs/Learn/Server-side/Django/Tutorial_local_library_website)
- [Django チュートリアル Part 2: ウェブサイトの骨組み作成](/ja/docs/Learn/Server-side/Django/skeleton_website)
- [Django チュートリアル Part 3: モデルの使用](/ja/docs/Learn/Server-side/Django/Models)
- [Django チュートリアル Part 4: Django 管理サイト](/ja/docs/Learn/Server-side/Django/Admin_site)
- [Django チュートリアル Part 5: ホームページの作成](/ja/docs/Learn/Server-side/Django/Home_page)
- [Django チュートリアル Part 6: 汎用の一覧表示と詳細表示](/ja/docs/Learn/Server-side/Django/Generic_views)
- [Django チュートリアル Part 7: セッションフレームワーク](/ja/docs/Learn/Server-side/Django/Sessions)
- [Django チュートリアル Part 8: ユーザー認証と権限](/ja/docs/Learn/Server-side/Django/Authentication)
- [Django チュートリアル Part 9: フォームの操作](/ja/docs/Learn/Server-side/Django/Forms)
- [Django チュートリアル Part 10: Django ウェブアプリケーションのテスト](/ja/docs/Learn/Server-side/Django/Testing)
- [Django チュートリアル Part 11: Django を本番環境にデプロイする](/ja/docs/Learn/Server-side/Django/Deployment)
- [Django ウェブアプリケーションセキュリティ](/ja/docs/Learn/Server-side/Django/web_application_security)
- [DIY Django ミニブログ](/ja/docs/Learn/Server-side/Django/django_assessment_blog)
