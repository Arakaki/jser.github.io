---
title: "2017-11-07のJS: TypeScript 2.6.、Node.js 8.9.0 LTS、Angular 5.0.0"
author: "azu"
layout: post
date : 2017-11-07T01:13:49.333Z
category: JSer
tags:
- TypeScript
- Node.js
- Angular

---

JSer.info #356 - TypeScript 2.6が正式にリリースされました。

- [Announcing TypeScript 2.6 | TypeScript](https://blogs.msdn.microsoft.com/typescript/2017/10/31/announcing-typescript-2-6/ "Announcing TypeScript 2.6 | TypeScript")

`strictFunctionTypes`オプションが有効時は、関数の引数がBivariantではなくContravariantとして扱われるようになりました。以前のTypeScriptはFlowとは異なり関数の引数の不整合をコンパイルエラーとしませんでしたが、今回の`strictFunctionTypes`オプションでその不整合をコンパイルエラーにできます。

- [なぜ TypeScript の型システムが健全性を諦めているか - Qiita](https://qiita.com/na-o-ys/items/aa56d678cdf0de2bdd79 "なぜ TypeScript の型システムが健全性を諦めているか - Qiita")

また`--locale`でのCLIやエラーメッセージの多言語化、`--watch`の改善、`// ts-ignore`のサポート。
languageserviceの改善でVSCodeなどでJSDocから型をQuickfixできるように、`@types`の自動インストール対応などが行われています。

詳しくは次の記事でも解説されています。

- [TypeScript 2.6 変更点と注意点 - abcdefGets](http://abcdef.gets.b6n.ch/entry/2017/11/01/101358)
- [TypeScript 2.6.1 変更点 - Qiita](https://qiita.com/vvakame/items/d2c7cf142fa0af39d2d5)

----

Node.js 8.9.0と9.0.0がリリースされました。

- [Node v8.9.0 (LTS) | Node.js](https://nodejs.org/en/blog/release/v8.9.0/)

Node.js 8.9.0では、npm 5.5.1へのアップデート、`require.resolve()`に指定パスを基準に探索するオプションが追加、`util.TextEncoder`と`util.TextDecoder`の実験フラグが外れています。
また、Node.js 8.9.0は8.x系のLong-Term Supported (LTS)となりました。

![LTS](https://cdn.rawgit.com/nodejs/Release/05e27d38230ae5077a3bb463933f5c2eeb33f981/schedule.png)

> [nodejs/Release: Node.js Foundation Release Working Group](https://github.com/nodejs/Release "nodejs/Release: Node.js Foundation Release Working Group")より

次の記事で詳細が書かれていますが、Node.js 4.xと6.xからのマイグレーションが推奨されています。

- [NEWS: Node.js 8 Moves into Long-Term Support and Node.js 9 Becomes the New Current Release Line](https://medium.com/the-node-js-collection/news-node-js-8-moves-into-long-term-support-and-node-js-9-becomes-the-new-current-release-line-74cf754a10a0 "NEWS: Node.js 8 Moves into Long-Term Support and Node.js 9 Becomes the New Current Release Line")

また、同時にNode.js 9.0.0がリリースされています。
Node.js 9.0.0では、さまざまなBreaking Changeが含まれています。

Error codeの対応、`assert.deepStrictEqual`がSameValueZeroのロジックで比較するようになり、`Intl.v8BreakIterator`や`domain`から`.dispose()`の削除などが行われています。

機能追加として、`assert`のメソッドがカスタムエラーをサポート、`util.callbackify`、`util.isDeepStrictEqual`の追加などが行われています。

詳細は次の記事を参照してください。

- [Node v9.0.0 (Current) | Node.js](https://nodejs.org/en/blog/release/v9.0.0/)

----

Angular 5.0.0がリリースされました。
また同時に[angular-cli](https://github.com/angular/angular-cli "angular-cli") 1.5.0がリリースされています。

- [Version 5.0.0 of Angular Now Available – Angular Blog](https://blog.angular.io/version-5-0-0-of-angular-now-available-37e414935ced)
- [angular/CHANGELOG.md at master · angular/angular](https://github.com/angular/angular/blob/master/CHANGELOG.md#500-pentagonal-donut-2017-11-01)
- [Release 1.5 – Turing · angular/angular-cli](https://github.com/angular/angular-cli/releases/tag/v1.5.0)

CLIでのビルドにBuild Optimizerがデフォルトで適応され、Decoratorなどランタイムでは不要なものを削除できるようになっています。
破壊的な変更としてi18n pipesのデフォルト挙動の変更やDateFormatがCLDRに合わせた書式へと変更されています。
偶然、同じ時期にCLDRの最新版であるCLDR 32もリリースされています。

- [Date formats - Google spread sheet](https://docs.google.com/spreadsheets/d/12iygt-_cakNP1VO7MV9g4lq9NsxVWG4tSfc98HpHb0k/edit#gid=0 "Date formats - Google spread sheet")
- [CLDR 32 Release Note - CLDR - Unicode Common Locale Data Repository](http://cldr.unicode.org/index/downloads/cldr-32 "CLDR 32 Release Note - CLDR - Unicode Common Locale Data Repository")

RxJS 5.5へのアップデート、Routerのライフサイクルの追加なども行われています。

AngularではLTSとして`4.x`系が公開されていて、`4.x`は2017年10月から2018年10月までのサポートとなっています。
詳細は次のページに公開されています。

- [Long-Term Supported (LTS) Versions](https://github.com/angular/angular/blob/master/docs/RELEASE_SCHEDULE.md#long-term-supported-lts-versions "Long-Term Supported (LTS) Versions")

----


<h1 class="site-genre">ヘッドライン</h1>

----

## Announcing TypeScript 2.6 | TypeScript
[blogs.msdn.microsoft.com/typescript/2017/10/31/announcing-typescript-2-6/](https://blogs.msdn.microsoft.com/typescript/2017/10/31/announcing-typescript-2-6/ "Announcing TypeScript 2.6 | TypeScript")
<p class="jser-tags jser-tag-icon"><span class="jser-tag">TypeScript</span> <span class="jser-tag">ReleaseNote</span></p>

TypeScript 2.6リリース。
`strictFunctionTypes`のサポート、`--locale`での多言語化、`--watch`の改善、`// ts-ignore`のサポート。
VSCodeなどでJSDocから型をQuickfixできるように、`@types`の自動インストール対応など

- [TypeScript 2.6 変更点と注意点 - abcdefGets](http://abcdef.gets.b6n.ch/entry/2017/11/01/101358 "TypeScript 2.6 変更点と注意点 - abcdefGets")
- [TypeScript 2.6.1 変更点 - Qiita](https://qiita.com/vvakame/items/d2c7cf142fa0af39d2d5 "TypeScript 2.6.1 変更点 - Qiita")

----

## NEWS: Node.js 8 Moves into Long-Term Support and Node.js 9 Becomes the New Current Release Line
[medium.com/the-node-js-collection/news-node-js-8-moves-into-long-term-support-and-node-js-9-becomes-the-new-current-release-line-74cf754a10a0](https://medium.com/the-node-js-collection/news-node-js-8-moves-into-long-term-support-and-node-js-9-becomes-the-new-current-release-line-74cf754a10a0 "NEWS: Node.js 8 Moves into Long-Term Support and Node.js 9 Becomes the New Current Release Line")
<p class="jser-tags jser-tag-icon"><span class="jser-tag">node.js</span> <span class="jser-tag">ReleaseNote</span></p>

Node.js 8.9.0がリリースされ8.xのLong-Term Support(LTS)となった。また同時に開発バージョンである9.xが公開された。

- [Node v8.9.0 (LTS) | Node.js](https://nodejs.org/en/blog/release/v8.9.0/ "Node v8.9.0 (LTS) | Node.js")
- [Node v9.0.0 (Current) | Node.js](https://nodejs.org/en/blog/release/v9.0.0/ "Node v9.0.0 (Current) | Node.js")

----

## Node v8.9.0 (LTS) | Node.js
[nodejs.org/en/blog/release/v8.9.0/](https://nodejs.org/en/blog/release/v8.9.0/ "Node v8.9.0 (LTS) | Node.js")
<p class="jser-tags jser-tag-icon"><span class="jser-tag">node.js</span> <span class="jser-tag">ReleaseNote</span></p>

Node.js 8.9.0リリース。8.x系のLTSとして公開された。
npm 5.5.1へのアップデート、`require.resolve()`に指定パスを探索するオプションが追加、`util.TextEncoder`と`util.TextDecoder`のフラグが外れるなど


----

## Node v9.0.0 (Current) | Node.js
[nodejs.org/en/blog/release/v9.0.0/](https://nodejs.org/en/blog/release/v9.0.0/ "Node v9.0.0 (Current) | Node.js")
<p class="jser-tags jser-tag-icon"><span class="jser-tag">node.js</span> <span class="jser-tag">ReleaseNote</span></p>

Node.js 9.0.0リリース。
Error codeの対応、`assert.deepStrictEqual`がSameValueZeroのロジックで比較するように、`assert`のメソッドがカスタムエラーをサポート、`util.callbackify`、`util.isDeepStrictEqual`の追加など。
また`Intl.v8BreakIterator`の削除されている。

- [What&#39;s new in Node.js 9?](https://nemethgergely.com/what-is-new-in-nodejs-9/ "What&amp;#39;s new in Node.js 9?")

----

## Version 5.0.0 of Angular Now Available – Angular Blog
[blog.angular.io/version-5-0-0-of-angular-now-available-37e414935ced](https://blog.angular.io/version-5-0-0-of-angular-now-available-37e414935ced "Version 5.0.0 of Angular Now Available – Angular Blog")
<p class="jser-tags jser-tag-icon"><span class="jser-tag">Angular</span> <span class="jser-tag">ReleaseNote</span></p>

Angular 5.0.0リリース。
CLIにBuild Optimizerがデフォルトで適応され、Decoratorなどランタイムでは不要なものを削除できるように。
i18n pipesのデフォルト挙動の変更やDateFormatの変更。
RxJS 5.5へのアップデート、Routerのライフサイクルの追加など

- [angular/CHANGELOG.md at master · angular/angular](https://github.com/angular/angular/blob/master/CHANGELOG.md#500-pentagonal-donut-2017-11-01 "angular/CHANGELOG.md at master · angular/angular")
- [Release 1.5 – Turing · angular/angular-cli](https://github.com/angular/angular-cli/releases/tag/v1.5.0 "Release 1.5 – Turing · angular/angular-cli")
- [Angular Update Guide - Beta](https://angular-update-guide.firebaseapp.com/ "Angular Update Guide - Beta")

----

## Release Notes for Safari Technology Preview 43 | WebKit
[webkit.org/blog/8016/release-notes-for-safari-technology-preview-43/](https://webkit.org/blog/8016/release-notes-for-safari-technology-preview-43/ "Release Notes for Safari Technology Preview 43 | WebKit")
<p class="jser-tags jser-tag-icon"><span class="jser-tag">safari</span> <span class="jser-tag">ReleaseNote</span></p>

Safari Technology Preview Release 43リリース。
Cache Storage APIがデフォルトで有効化、`createImageBitmap`と`drawImage(imageBitmap)`のサポート。
Web Inspectorで新しいネットワークタブ、Canvasタブの有効化、HARエクスポートに対応など

- [CacheStorage - Web APIs | MDN](https://developer.mozilla.org/en-US/docs/Web/API/CacheStorage "CacheStorage - Web APIs | MDN")
- [ImageBitmap - Web API インターフェイス | MDN](https://developer.mozilla.org/ja/docs/Web/API/ImageBitmap "ImageBitmap - Web API インターフェイス | MDN")

----

## Element 2.0 is here – ELEME Frontend Engineering – Medium
[medium.com/elemefe/element-2-0-is-here-71bfa217e269](https://medium.com/elemefe/element-2-0-is-here-71bfa217e269 "Element 2.0 is here – ELEME Frontend Engineering – Medium")
<p class="jser-tags jser-tag-icon"><span class="jser-tag">Vue</span> <span class="jser-tag">ReleaseNote</span> <span class="jser-tag">library</span></p>

Vue向けのUIフレームワークのElement 2.0リリース


----
<h1 class="site-genre">アーティクル</h1>

----

## Introducing new JavaScript optimizations, WebAssembly, SharedArrayBuffer, and Atomics in EdgeHTML 16 - Microsoft Edge Dev BlogMicrosoft Edge Dev Blog
[blogs.windows.com/msedgedev/2017/10/31/optimizations-webassembly-sharedarraybuffer-atomics-edgehtml-16/](https://blogs.windows.com/msedgedev/2017/10/31/optimizations-webassembly-sharedarraybuffer-atomics-edgehtml-16/ "Introducing new JavaScript optimizations, WebAssembly, SharedArrayBuffer, and Atomics in EdgeHTML 16 - Microsoft Edge Dev BlogMicrosoft Edge Dev Blog")
<p class="jser-tags jser-tag-icon"><span class="jser-tag">MSEdge</span> <span class="jser-tag">browser</span> <span class="jser-tag">JavaScript</span> <span class="jser-tag">article</span></p>

MSEdge 16の変更点について。
特定のスコープの関数を遅延実行できるようにしパフォーマンスの改善、try-catch-finallyの最適化、
WebAssemblyとSharedArrayBufferをデフォルトで有効化など


----

## Common TypeScript Error Messages - Blog | SitePen
[www.sitepen.com/blog/2017/11/01/common-typescript-error-messages/](https://www.sitepen.com/blog/2017/11/01/common-typescript-error-messages/ "Common TypeScript Error Messages - Blog | SitePen")
<p class="jser-tags jser-tag-icon"><span class="jser-tag">TypeScript</span> <span class="jser-tag">article</span></p>

TypeScriptのよく見るエラーとその解決方法について


----

## Houdini Paint API | blog.jxck.io
[blog.jxck.io/entries/2017-10-31/houdini-paint-api.html](https://blog.jxck.io/entries/2017-10-31/houdini-paint-api.html "Houdini Paint API | blog.jxck.io")
<p class="jser-tags jser-tag-icon"><span class="jser-tag">CSS</span> <span class="jser-tag">article</span></p>

CSS Paint APIについての解説とデモ


----

## How to debug Front-end: Console – Pragmatists
[blog.pragmatists.com/how-to-debug-front-end-console-3456e4ee5504](https://blog.pragmatists.com/how-to-debug-front-end-console-3456e4ee5504 "How to debug Front-end: Console – Pragmatists")
<p class="jser-tags jser-tag-icon"><span class="jser-tag">browser</span> <span class="jser-tag">Chrome</span> <span class="jser-tag">debiug</span></p>

ブラウザの開発者ツールのConsole APIの紹介


----

## Put Your Webpack Bundle On A Diet - Part 1
[www.contentful.com/blog/2017/10/10/put-your-webpack-on-a-diet-part-1/](https://www.contentful.com/blog/2017/10/10/put-your-webpack-on-a-diet-part-1/ "Put Your Webpack Bundle On A Diet - Part 1")
<p class="jser-tags jser-tag-icon"><span class="jser-tag">webpack</span> <span class="jser-tag">performance</span> <span class="jser-tag">article</span></p>

webpackでbundleファイルサイズの最適化についての連載。
Part 1ではminify、production buildなどの基本的なことを扱っている。
tree shaking、momentやlodashなどから不要なものを削除、babel-preset-env でのpolyfillの最適化など

- [Put Your Webpack Bundle On A Diet - Part 2](https://www.contentful.com/blog/2017/10/19/put-your-webpack-bundle-on-a-diet-part-2/ "Put Your Webpack Bundle On A Diet - Part 2")
- [Put Your Webpack Bundle On A Diet - Part 3](https://www.contentful.com/blog/2017/10/27/put-your-webpack-bundle-on-a-diet-part-3/ "Put Your Webpack Bundle On A Diet - Part 3")

----

## Tracing method calls via Proxies
[2ality.com/2017/11/proxy-method-calls.html](http://2ality.com/2017/11/proxy-method-calls.html "Tracing method calls via Proxies")
<p class="jser-tags jser-tag-icon"><span class="jser-tag">JavaScript</span> <span class="jser-tag">proxy</span> <span class="jser-tag">article</span></p>

ES proxyを使ったメソッド呼び出しのロギングについて


----

## Node.jsのパフォーマンスチューニングのtips - 技術探し
[abouthiroppy.hatenablog.jp/entry/2017/11/06/095943](http://abouthiroppy.hatenablog.jp/entry/2017/11/06/095943 "Node.jsのパフォーマンスチューニングのtips - 技術探し")
<p class="jser-tags jser-tag-icon"><span class="jser-tag">node.js</span> <span class="jser-tag">performance</span> <span class="jser-tag">article</span></p>

Node.jsのデバッグ、Trace系オプション紹介


----
<h1 class="site-genre">スライド、動画関係</h1>

----

## プロダクトに 1 から Vue.js を導入した話
[www.slideshare.net/ShoheiOkada/1-vuejs](https://www.slideshare.net/ShoheiOkada/1-vuejs "プロダクトに 1 から Vue.js を導入した話")
<p class="jser-tags jser-tag-icon"><span class="jser-tag">Vue</span> <span class="jser-tag">slide</span> <span class="jser-tag">opinion</span></p>

jQueryベースだったシステムに、Vueを導入してみての話。
チームへの導入や導入前後での違いについてなど


----
<h1 class="site-genre">ソフトウェア、ツール、ライブラリ関係</h1>

----

## Server.js - server.js
[serverjs.io/](https://serverjs.io/ "Server.js - server.js")
<p class="jser-tags jser-tag-icon"><span class="jser-tag">node.js</span> <span class="jser-tag">server</span> <span class="jser-tag">library</span></p>

シンプルなNode.jsのサーバライブラリ


----

## Atomic CSS
[acss.io/](https://acss.io/ "Atomic CSS")
<p class="jser-tags jser-tag-icon"><span class="jser-tag">CSS</span> <span class="jser-tag">library</span> <span class="jser-tag">Tools</span></p>

宣言したクラスを元にCSSを作成するフレームワーク/ツール。


----

## raphamorim/react-tv: \[WIP\] React development for TV (Renderer for low memory applications and Packager for WebOS, Tizen, Orsay) 📺
[github.com/raphamorim/react-tv](https://github.com/raphamorim/react-tv "raphamorim/react-tv: \[WIP\] React development for TV (Renderer for low memory applications and Packager for WebOS, Tizen, Orsay) 📺")
<p class="jser-tags jser-tag-icon"><span class="jser-tag">React</span> <span class="jser-tag">TV</span> <span class="jser-tag">library</span></p>

WebOSなどのTV向けのReactツールキット。
Rendererや開発環境、ツールなどをまとめたもの


----
<h1 class="site-genre">書籍関係</h1>

----

## React Bits · GitBook
[www.gitbook.com/book/vasanthk/react-bits/details](https://www.gitbook.com/book/vasanthk/react-bits/details "React Bits · GitBook")
<p class="jser-tags jser-tag-icon"><span class="jser-tag">React</span> <span class="jser-tag">book</span></p>

ReactのパターンやTips、アンチパターンについてまとめられた電子書籍


----
