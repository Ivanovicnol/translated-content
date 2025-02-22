---
title: '<portal>: ポータル要素'
slug: Web/HTML/Element/portal
tags:
  - Content
  - Element
  - Embedded content
  - Embedding
  - HTML
  - HTML embedded content
  - Reference
  - Web
  - Portal
translation_of: Web/HTML/Element/portal
---
{{HTMLRef}}

**HTML のポータル要素 (`<portal>`)** は、他の HTML ページを現在のページに埋め込み、新しいページへの移動がスムーズにできるようにします。

`<portal>` は `<iframe>` に似ています。 `<iframe>` では独立した{{Glossary("browsing context", "閲覧コンテキスト")}}を作成して埋め込みます。しかし、 `<portal>` で埋め込まれるコンテンツは `<iframe>` の場合よりも制限されます。これを操作することはできませんので、文書にウィジェットを埋め込むには適していません。その代わり、 `<portal>` は他のページのコンテンツのプレビューとして動作します。そのため、埋め込まれたコンテンツへのシームレスな遷移により移動を行うことができます。

<table class="properties">
  <tbody>
    <tr>
      <th scope="row">暗黙の ARIA ロール</th>
      <td>
        <a href="/ja/docs/Web/Accessibility/ARIA/Roles/button_role">button</a>
      </td>
    </tr>
    <tr>
      <th scope="row">DOM インターフェイス</th>
      <td>{{domxref("HTMLPortalElement")}}</td>
    </tr>
  </tbody>
</table>

## 属性

この要素には[グローバル属性](/ja/docs/Web/HTML/Global_attributes)があります。

- {{htmlattrdef("referrerpolicy")}}
  - : [リファラーポリシー](/ja/docs/Web/HTTP/Headers/Referrer-Policy)を設定します。これは、 `src` 属性の値で指定された URL のページをリクエストする際に使用されます。
- {{htmlattrdef("src")}}
  - : 埋め込むページの URL です。

## 例

### 基本的な例

以下の例は `https://example.com` のコンテンツをプレビューとして埋め込みます。

```html
<portal id="exampleportal" src="https://example.com/"></portal>
```

## アクセシビリティの考慮

`<portal>`が表示するプレビューは、操作が可能ではないため、入力イベントやフォーカスを受けません。そのため、ポータルの埋め込みコンテンツは、{{Glossary("accessibility tree", "アクセシビリティツリー")}}の要素として公開されません。ポータルは、ボタンのように移動してアクティブにすることができ、クリックしたときの既定の動作は、ポータルを有効にすることです。

ポータルには、埋め込まれたページのタイトルが既定のラベルが与えられます。タイトルがない場合は、プレビューで表示されるテキストが結合されてラベルが作成されます。 {{htmlattrxref("aria-label")}} 属性を使用すると、これを上書きすることができます。

事前レンダリングのためにポータルを使用する場合は、 HTML の hidden 属性または CSS の {{cssxref("display")}} プロパティの値を `none` にして非表示にしてください。

ポータルがアクティブ化している間にアニメーションを使用する場合は、 {{cssxref("@media/prefers-reduced-motion", "prefers-reduced-motion")}} [メディア特性](/ja/docs/Web/CSS/@media#メディア特性)を尊重してください。

## 仕様書

| 仕様書                           | 状態                         | 備考     |
| -------------------------------- | ---------------------------- | -------- |
| {{SpecName('Portals')}} | {{Spec2('Portals')}} | 初回定義 |

## ブラウザーの互換性

{{Compat("html.elements.portal")}}
