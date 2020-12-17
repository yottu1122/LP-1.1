# ランディングページを作ってみよう！

## セットアップ

今回はすでにデザインされているデータをもとに全く同じデザインのサイトを作ってもらいます。
デザインのデータはこちらのサイトからフォトショップのデータをダウンロードをします。
実際はフォトショップから素材を取ってきますが、今回はこちらで用意したzipデータをダウンロードしてください。
また今回のデータは横幅が1600pxになります。
実際にサイトを閲覧するのは人それぞれ違うので大きさを計算しなければいけません。
計算を行うことで余白の大きさや画像の大きさなどでバランスが崩れることなく作ることができます。
また今回はリセットcssというものを入れています。

### リセットcssとは

リセットCSS は、ブラウザごとの表示の違いをリセットしてくれるCSSファイルです。

ブラウザにはEdgeやChrome、Safariなど、様々なものがあります。
しかし、そういったブラウザの違いを意識せずにサイトを作ると、ブラウザによって異なる見た目になってしまうため、レイアウトが崩れてしまったりといったことが起こります。

そういったブラウザによる見え方の違いを揃えてくれるのがリセットCSSです。
これを使うことによって、ブラウザごとの違いを意識せずにコーディングができ、サイト制作が楽になります。

## 意識する点

今回作成してもらうに当たって意識しなければいけない点が、デザインを再現することです。
この再現というのが、余白が１pxでも連れてはいけません。文字の大きさも1pxも違ってはいけません。
ぴったり同じ大きさにしなければいけません。

## 理由
業務ではデザインが完成した状態でデータが送られてきます。
そのデザインというのはクライアント側が作って欲しいWebサイトになります。
そのデザイン通りに作らなければ、クライアントのデザインとは違うものを作ってしまいます。

## HTMLを書いて行こう！

ではHTMLを書いていきます。
まずはテンプレートを書いていきます。

```html
<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <title>LP練習</title>
    <link rel="stylesheet" href="css/style.css">
    <link href="normalize.css/normalize.css" rel="stylesheet"/>
</head>
<body>
    
</body>
</html>

```
## header

今回は各セクションごとにコードを分けていきます。
まずは<header>を作っていきます。

```html
<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <title>LP練習</title>
    <link rel="stylesheet" href="css/style.css">
</head>
<body>
    <header class="side-header">
      <div class="logo"><img src="img/city.png"/></div>
      <nav>
        <ul class="nav-memu">
          <li class="nav-content">サービス</li>
          <li class="nav-content">ニュース</li>
          <li class="nav-content">CSR</li>
          <li class="nav-content">IR情報</li>
          <li class="nav-content">会社情報</li>
          <li class="nav-content">採用情報</li>
          <li class="contact">お問い合わせ</li>
        </ul>
      </nav>
    </header>
</body>
</html>

```
<img src=img/web1.png>

このようになれば成功です。
<header>というタグはヘッダーを示すものになります。
なくても影響はありませんが、<header>を指定することで、より読み取りやすいコードになるので、
今回は指定していきます。

<nav>も<header>と意味合いは同じになります。
ナビゲーションを示すものになるので特になくても影響はありませんが、今回は指定します。

次にcssの設定をしていきます。

```css
.side-header {
  display: flex;
  justify-content: space-between;
}

.side-header img {
  margin-top: 30px;
  margin-left: 20px;
}
```

まずは横並びにしていきます。
display:flexを使うことで要素を横並びにすることができます。
次にjustify-content: space-between;で位置を指定します。

次にロゴの位置を調節します。
 margin-top: 30px;  margin-left: 20px;を指定することで余白を調節しています。

 ```css

.nav-memu {
  margin: 0;
}

ul {
  list-style: none;
}

li {
  padding-top: 30px;
  padding-bottom: 30px;
}

.contact {
  margin-left: 90px;
  background-color: #30d0ed;
  color: #fff;
  display: block;
  width: 200px;
  text-align: center;
}

 ```

次にnavの設定行います。
ここで重要となるのは.contactの部分になります。
liの中で唯一クラスが異なリます。
個別で設定していく必要がある部分なのでクラス名を一緒にしないようにしましょう。

```css
.nav-memu {
  display: flex;
}

.nav-memu li {
  font-size: 14px;
}

.nav-content {
  margin-left: 80px;
}

```

最後にfont-sizeと余白を整えていきます。

<img src=img/web2.png>

このようになれば成功です。

次にメインの部分を作っていきます。

## main

まずはmainの部分を作っていきます。

```html
<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <title>LP練習</title>
    <link rel="stylesheet" href="css/style.css">
</head>
<body>
    <header class="side-header">
      <div class="logo"><img src="img/city.png"/></div>
      <nav>
        <ul class="nav-memu">
          <li class="nav-content">サービス</li>
          <li class="nav-content">ニュース</li>
          <li class="nav-content">CSR</li>
          <li class="nav-content">IR情報</li>
          <li class="nav-content">会社情報</li>
          <li class="nav-content">採用情報</li>
          <li class="contact">お問い合わせ</li>
        </ul>
      </nav>
    </header>
    <main>

    </main>
</body>
</html>
```
今回はこのmainにsectionを設定します。
mainとsectionも特にコードに影響はありませんが、どの部分のコードかを明確化させるために書いていきます。

```html
<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <title>LP練習</title>
    <link rel="stylesheet" href="css/style.css">
</head>
<body>
    <header class="side-header">
      <div class="logo"><img src="img/city.png"/></div>
      <nav>
        <ul class="nav-memu">
          <li class="nav-content">サービス</li>
          <li class="nav-content">ニュース</li>
          <li class="nav-content">CSR</li>
          <li class="nav-content">IR情報</li>
          <li class="nav-content">会社情報</li>
          <li class="nav-content">採用情報</li>
          <li class="contact">お問い合わせ</li>
        </ul>
      </nav>
    </header>
    <main>
      <section class="main-img">
        <div class="back">
            <img class="main-title" src="img/Specialist.png" alt="logo"/>
        </div>
        <div class="sub">  
            <img class="sub-title" src="img/subtitle.png" alt="logo"/>
        </div>
      </section>
    </main>
</body>
</html>
```

今回sectionの中には今回使う画像データを入れます。
このsectionには画像のみ入れます。
次に背景の画像の設定をするためにcssを書いていきます。

```css
main{
    height: 667px;
    background-image: url("../img/background.png");
    z-index: 1;
}

.main-img{
    height: 668px;
}


.back{
    text-align: center;
}

.main-title{
    margin-top: 150px;
}

.sub{
    text-align: center;
}


```

<img src=img/web3.png>

このようになれば成功です。

