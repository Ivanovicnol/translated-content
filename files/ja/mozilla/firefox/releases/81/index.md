---
title: Firefox 81 for developers
slug: Mozilla/Firefox/Releases/81
tags:
  - '81'
  - Firefox
  - Mozilla
  - Release
translation_of: Mozilla/Firefox/Releases/81
---
{{FirefoxSidebar}}

このページでは、開発者に影響する Firefox 81 の変更点をまとめています。Firefox 81 は 2020 年 9 月 22 日にリリースされました。

## ウェブ開発者向けの変更点一覧

### 開発者ツール

- [デバッガー](/ja/docs/Tools/Debugger) で、`.ts` および `.tsx` ファイルに対して TypeScript のアイコンを使用するようになりました ({{bug(1642769)}})。以前は汎用ファイルのアイコンを使用していました。
- [デバッガーのソースペイン](/ja/docs/Tools/Debugger/UI_Tour#Source_pane) で行の折り返しをサポートしました ({{bug(1590885)}})。
- [アクセシビリティインスペクター](/ja/docs/Tools/Accessibility_inspector) から、不必要な [色覚シミュレーション](/ja/docs/Tools/Accessibility_inspector/Simulation) (1 型 3 色覚、2 型 3 色覚、3 型 3 色覚) を削除して、1 色覚 (全色盲) のシミュレーションを追加しました ({{bug(1655053)}})。
- [要素にクラスを追加する](/ja/docs/Tools/Page_Inspector/How_to/Examine_and_edit_CSS#Viewing_and_changing_classes_on_an_element) 際のオートコンプリートをサポートしました。文書内にあるクラスに基づいて、クラスを提案します ({{bug(1492797)}})。

### HTML

- サンドボックス化された [`<iframe>`](/ja/docs/Web/HTML/Element/iframe) 要素で、自動ダウンロードをブロックするようになりました ({{bug(1558394)}})。

#### 廃止

- 非標準の `mozallowfullscreen` 属性を、[`<iframe>`](/ja/docs/Web/HTML/Element/iframe) から削除しました。代わりに `allow="fullscreen"` を検討してください ({{bug(1657599)}})。

### CSS

- {{CSSxRef("overflow")}} プロパティの値 `overflow:-moz-hidden-unscrollable` を改名して、値 `clip` をサポートしました ({{bug(1531609)}})。
- 仕様書に合わせて、{{CSSxRef("text-combine-upright")}} プロパティをアニメーション不可にしました ({{bug(1654195)}})。

#### 廃止

- 非標準の {{CSSxRef("::-moz-focus-outer")}} [疑似要素](/ja/docs/Web/CSS/Pseudo-elements) を削除しました ({{bug(1655859)}})。

### JavaScript

_変更なし。_

### HTTP

- Firefox で、空白を含むクォートされていないファイル名を持つ非標準の [`Content-Disposition`](/ja/docs/Web/HTTP/Headers/Content-Disposition) ヘッダーを受け入れるようになりました ({{bug(1440677)}})。
- Firefox で HTTP [`Feature-Policy`](/ja/docs/Web/HTTP/Headers/Feature-Policy) ヘッダーの [`web-share`](/ja/docs/Web/HTTP/Headers/Feature-Policy/web-share) ディレクティブをサポートしました。これは、[Web Share API](/ja/docs/Web/API/Navigator/share) へのアクセスを信頼されたオリジンに制限するために使用できます。現時点で Firefox は Web Share API 自体をサポートしていないことに注意してください ({{bug(1653199)}})。

### API

#### ゲームパッド

- ゲームパッドのジョイスティックがアクティブになるしきい値を上げました。これにより、アイドル時に小さな軸の値を送信するコントローラーや、ごく小さな打撃によって意図せずゲームパッドがアクティブになる可能性を減らします。({{bug(1539178)}})

#### Workers/Service workers

- worker や shared worker のスクリプトで、厳格な MIME タイプの確認を強制するようになりました。すなわち {{domxref("Worker.Worker()", "Worker()")}} や {{domxref("SharedWorker.SharedWorker()", "SharedWorker()")}} コンストラクターの対象になるスクリプトは `text/javascript` で提供しなければなりません ({{bug(1523706)}})。

### WebDriver conformance (Marionette)

- `setWindowRect` 機能の既定値が、すべてのデスクトップアプリケーション (Thunderbird を含む) で `true` に、Android の GeckoView で `false` になりました ({{bug(1650872)}})。
- 以下のコマンドで Fission をサポートしました: `WebDriver:SwitchToFrame`、`WebDriver:SwitchToParentFrame`、`WebDriver:GetCurrentURL`。すべての Fission 互換コマンドは、`marionette.actors.enabled` が `true` に設定されている場合に限って利用できます。
- 新しいウィンドウを開いた後、ブラウジングコンテキストの監視が破損する問題を修正しました ({{bug(1661495)}})。
- `WebDriver:SwitchToWindow` が失敗したとき、統一された `NoSuchWindowError` が常に返るようになりました ({{bug(1663429)}})。

#### 廃止

- WebDriver 仕様書に含まれておらず、またすでに使用されていない `WebDriver:GetActiveFrame` を削除しました ({{bug(1659502)}})。

## アドオン開発者向けの変更点

- [`tabs.saveAsPDF()`](/ja/docs/Mozilla/Add-ons/WebExtensions/API/tabs/saveAsPDF) を macOS でサポートしました ({{bug(1653354)}})。
- [`webNavigation.getFrame()`](/ja/docs/Mozilla/Add-ons/WebExtensions/API/webNavigation/getFrame) および [`webNavigation.getAllFrames()`](/ja/docs/Mozilla/Add-ons/WebExtensions/API/webNavigation/getAllFrames) の動作を変更しました。次のページへ進んでタブが破棄されたとき、promise が `null` 値で解決します ({{bug(1654842)}})。

## 過去のバージョン

{{Firefox_for_developers(80)}}
