# Maki

## A Basic Lightweight LESS Boilerplate

Maki は、LESS で勢いよくサイト制作する人のための Boilerplate です。

「サイトをフルスクラッチするときに CSS (LESS) の下準備が大変だなァ」みたいな時に使うと、スムーズに LESS を書き始められます。一般的な CSS フレームワークみたく厚くなく、本当に最初の下ごしらえの部分しか書いていないので、各々の LESS の書き方を邪魔せず使えます。   
[@sanographix](http://twitter.com/sanographix) が作っています。



# Get Started

まず[ここからダウンロード](https://github.com/sanographix/maki/archive/master.zip)してください。

次に html の head 部分に`maki.css`を読み込みます。

	<link rel="stylesheet" href="css/maki.css" />


# 中身

中身はこうなってます。maki.less だけをコンパイルすれば良いです。

	maki.less
	┣ _normalize.less
	┣ _mixin.less
	┣ _variable.less
	┗ _media-queries.less


## _normalize.less


[normalize.css](http://necolas.github.io/normalize.css/) です。


## _mixin.less

便利なmixinセットです。

また、classの(@foo, @bar)に適当な値を入れるとmixinの対応する変数に出力されます。例えばbox-shadowだったら

	.box-shadow(0px,5px,10px,#000);

と書くと

    -moz-box-shadow: 0px 5px 10px #000;
    -webkit-box-shadow: 0px 5px 10px #000;
    box-shadow: 0px 5px 10px #000;

になります。

使えるクラスは以下の通りです。

### よく使うの

| class | Mixin |
|-------|-----|
|.clear;|clear: both;|
|.clearfix|clearfixします|
|.inline-block|`inline-block`のIE7対応版です|
|.replace|テキストを画像置換するときにこれを呼び出すと便利です|
  
  
### ベンダープレフィックスついてる系の

| class | Mixin |
|-------|-----|
|.box-shadow(@x @y @blur @color);|box-shadow: @x @y @blur @color;|
|.box-shadow-inset(@x @y @blur @color); | box-shadow: inset @x @y @blur @color; |
|.text-shadow(@x @y @blur @color);| text-shadow: @x @y @blur @color; |
|.border-radius(@topright, @bottomright, @bottomleft, @topleft);|border-top-right-radius: @topright;<br/>border-bottom-right-radius: @bottomright;<br/>border-bottom-left-radius: @bottomleft;<br/>border-top-left-radius: @topleft; |
|.border-radius(@radius);| border-radius: @radius; |
|.gradient(@color,@start,@stop);| background-color: @color;<br/>background: linear-gradient(top, @start, @stop);|
|.opacity(@opacity);|opacity: @opacity;|
|.ellipsis;|text-overflow: ellipsis;|
|.transition(@duration, @ease);|    transition: all @duration @ease;|
|.transition-duration(@duration);|transition-duration: @duration;|
|.rotation(@deg);|transform: rotate(@deg);|
|.scale(@ratio);|.transform:scale(@ratio);|
|.translate(@x,@y);|.translate(@x, @y);|


## _variable.less
  
サイトで使う色はここに書いておいて、変数から呼び出すと便利です。使い方はこんな感じ。


	body {
	    background: @bg;
	    color: @base;
	}

	a {
	    color: @link;
	    border-color: @border;	
	    &:hover {
	        color: @hover;
	    }
	}


## _media-queries.less
  
メディアクエリです。Retina ディスプレイ用のスタイルを書く欄と、レスポンシブデザイン用のスタイルを書く欄があります。

Retina ディスプレイ用のスタイルは下記の 3 パターンに出し分けできます。

* Retina ディスプレイ用
	* Retina のデバイス全部に出す
	* Retina かつ iPad 以上のブラウザ幅のとき出す
	* Retina かつ PC で見てるときだけ出す
    
# Changelog

### 0.1 (August 06, 2013)

* とりあえず公開


# FAQ

#### Q: なんで Maki なの？

* [察してください](https://www.google.co.jp/search?q=%E8%A5%BF%E6%9C%A8%E9%87%8E%E7%9C%9F%E5%A7%AB)。


# License

The MIT License (MIT)

Copyright (c) 2013 SANOGRAPHIX

Permission is hereby granted, free of charge, to any person obtaining a copy of
this software and associated documentation files (the "Software"), to deal in
the Software without restriction, including without limitation the rights to
use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of
the Software, and to permit persons to whom the Software is furnished to do so,
subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS
FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR
COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER
IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN
CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

### Major Components

* Normalize.css: Public Domain
