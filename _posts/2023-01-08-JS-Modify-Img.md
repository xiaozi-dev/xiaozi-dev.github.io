---
title: アセット集からランダムに画像をサイトに表示させる方法
category: "JavaScript"
tags: [Web development, JavaScript]
---

&nbsp;&nbsp;昔HTMLとCSSを勉強していた時、静的なサイトしか作れなくて、サイトがリフレッシュされる度にHTMLの要素を自動的に変更させる方法を知らないまま勉強を止めました。その疑問はずっと残っていて、最新やっと真面目にウェブ開発を勉強すると決心して、JavaScriptを勉強し始めました。この記事にて、HTML要素の一つである画像をどのように自動的に変更させるかを書きます。

&nbsp;&nbsp;例えば、以下のようなHTMLがあります。サイトに表示しているのはimgのsrcで指定している画像です。imagesというフォルダーに、a.png~g.pngのアルファベット順の名前になっている画像ファイルは7つあります。どのようにsrcが指定している画像をサイトのリフレッシュとともにa.png~g.pngの範囲でランダムに自動的に変動させますでしょうか？
```html
　　 <div class="image">
        <p>image1</p>
        <img class="img1" src="images/a.png">
    </div>
```
&nbsp;&nbsp;変数を作って、ランダムに生成される画像のパスを変数に入れて、HTMLがその変数の値を読み取ることで実現できるということは、なぜか最初に考え出した方法です。残念ですが、HTMLは変数の値を読み取れる言語ではありません。この時はJavaScriptの出番です。JavaScriptを使ってDomから該当のimg srcを特定し、JavaScriptのメソッドでsrcの値を変更させることで実現できます。
&nbsp;&nbsp;HTMLとリンクしているJavaScriptファイルに、以下のようなscriptを書けば完了です。
```js
var randomNumber = Math.floor(((Math.random())*7 + 1));

document.querySelector(".img1").src = "images/" + randomNumber + ".png";
```
&nbsp;&nbsp;ちなみに、直接srcの値を変えるという考え方ではなく、imgの属性であるsrcの値を変えるという考え方でも良いです。言葉で何の違いがあるか分かりづらいですが、コードを見ると何のことを言っているかは分かりやすいです。
```js
var randomNumber = Math.floor(((Math.random())*7 + 1));

document.querySelector(".img1").setAttribute("src", "images/" + randomNumber +".png");
```

参考：[Udemy - The Complete 2023 Web Development Bootcamp](https://www.udemy.com/course/the-complete-web-development-bootcamp/)