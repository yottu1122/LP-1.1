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
    <link href="css/destyle.css" rel="stylesheet"/>
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
    <link href="css/destyle.css" rel="stylesheet"/>
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
    <link href="css/destyle.css" rel="stylesheet"/>
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
    <link href="css/destyle.css" rel="stylesheet"/>
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

次にNewsの部分を作っていきます。

まずはsectionを書いていきます。
```html
<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <title>LP練習</title>
    <link rel="stylesheet" href="css/style.css">
    <link href="css/destyle.css" rel="stylesheet"/>
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
      <section>

      </section>
    </main>
</body>
</html>
```

新しくsectionを作ることで次のフェーズにいくことがわかりやすくなります。
次にNewsのコンテンツを入れていきます。

```html
<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <title>LP練習</title>
    <link rel="stylesheet" href="css/style.css">
    <link href="css/destyle.css" rel="stylesheet"/>
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
      <section>
          <div class="news">
            <div class="news-title"><img src="img/News.png" alt="news"/>
              <p>一覧をみる></p>
            </div>
          </div>
      </section>
    </main>
</body>
</html>
```

次にcssを書いていきます。
今回はnews-titleのcssを書いていきます。
```css
.news {
  background-color: #edfcff;
  padding-left: 10%;
  display: flex;
  padding-bottom: 64px;
}

.news-title {
    margin-top: 4%;
    margin-left: 10%;
}

.news-sub{
    margin-top: 17px;
}
```
<img src=img/web4.png>
このようになれば成功になります。


次にnewsの内容を書いていきます。

```html
<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <title>LP練習</title>
    <link rel="stylesheet" href="css/style.css">
    <link href="css/destyle.css" rel="stylesheet"/>
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
      <section>
          <div class="news">
            <div class="news-title"><img src="img/News.png" alt="news"/>
              <p>一覧をみる></p>
            </div>
             <div class="news-topics">
              <div class="news-content">
                <p class="date">2020.03.14</p>
                <p class="label">プレス</p>
                <p class="description">【東京オリンピック会場跡地再開発計画】複合スポーツ施設及び新テーマパーク工事開始のお知らせ                                            </p>
              </div>
              <div class="news-content1">
                <p class="date">2020.02.30</p>
                <p class="label1">IR</p>
                <p class="description1"> 2019年9月期 第1四半期決算説明会動画</p>
              </div>
              <div class="news-content1">
                <p class="date">2020.02.30</p>
                <p class="label1">IR</p>
                <p class="description1"> 2019年9月期 第1四半期決算説明会動画</p>
              </div>
            </div>
          </div>
      </section>
    </main>
</body>
</html>
```

今回classの付け方は付け方は最初の部分はnews-contentでそのあとの二つには
news-content1にしています。
これは同じコードを書かないようにしています。

できるだけ同じものはclassでまとめるようにしましょう。

次にcssを書いていきます。

ここではdateとnews-contentとnews-content1の設定していきます。

```css

.date{
    margin-right: 10px;
}

.date1{
    margin-right: 10px;
    margin-top: 14px;
}


.label{
    background-color: #019bdf;
    padding: 4px 26px 4px 26px;
    margin-bottom: 10px;
    color: #fff;
}

.label1{
    background-color: #019bdf;
    padding: 4px 39px 4px 39px;
    margin-top: 10px;
    margin-bottom: 10px;
    color: #fff;
}

.news-content{
    display: flex;
    margin-left: 50px;
    margin-top: 74px;
    width: 100%;
    border-bottom: 0.5px solid;
    border-color: #93deff;
}

.news-content1{
    display: flex;
    margin-left: 50px;
    width: 100%;
    border-bottom: 0.5px solid;
    border-color: #93deff;
}
```

ここではcontentのcssを整えています。

margin-leftの数値が違うので今回はnews-contentとnews-content1を分けています。  
次に灰色の画像を表示します。

```html
<!DOCTYPE html>
<html lang="jp">
  <head>
    <meta charset="UTF-8"/>
    <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
    <link rel="stylesheet" href="css/style.css"/>
    <link href="css/destyle.css" rel="stylesheet"/>
    <title>lp</title>
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
        <div class="back"><img class="main-title" src="img/Specialist.png" alt="logo"/></div>
        <div class="sub">  <img class="sub-title" src="img/subtitle.png" alt="logo"/></div>
      </section>
      <section>
        <div class="news">
          <div class="news-title"><img src="img/News.png" alt="news"/>
            <p>一覧をみる></p>
          </div>
          <div class="news-topics">
            <div class="news-content">
              <p class="date">2020.03.14</p>
              <p class="label">プレス</p>
              <p class="description">【東京オリンピック会場跡地再開発計画】複合スポーツ施設及び新テーマパーク工事開始のお知らせ                                            </p>
            </div>
            <div class="news-content1">
              <p class="date">2020.02.30</p>
              <p class="label1">IR</p>
              <p class="description1"> 2019年9月期 第1四半期決算説明会動画</p>
            </div>
            <div class="news-content1">
              <p class="date">2020.02.30</p>
              <p class="label1">IR</p>
              <p class="description1"> 2019年9月期 第1四半期決算説明会動画</p>
            </div>
          </div>
        </div>
      </section>
      <section>
        <div class="work">
          <div class="work-title"><img src="img/Service.png" alt="work"/></div>
          <div class="work-sub">  <img src="img/citylab.png" alt="work"/></div>
          <div class="work-content"><img class="contents1" src="img/content.png" alt="work"/><img class="contents2" src="img/content.png" alt="work"/><img class="contents3" src="img/content.png" alt="work"/></div>
        </div>
      </section>
    </main>
  </body>
</html>
```

まずはsectionを作ります。
次に今回の部分となるworkを書いていきます。
workの中にはtitle画像とsub画像とcontentを入れています。
ここではcontent内のないのclassを別々にか行く必要はあるので一緒にはしないでください。
次にcssを設定していきます。

```css
.work{
    text-align: center;
}

.work-title{
    margin-top: 75px;
}

.work-sub{
    margin-bottom: 22px;
}

.contents1{
    margin-left: 10%;
    margin-right: 15px;
    width: 24%;
}

.contents2{
    margin-left: 15px;
    margin-right: 15px;
    width: 24%;
}

.contents3{
    margin-left: 15px;
    margin-right: 10%;
    width: 24%;
}

```

<img src=img/web6.png>
このようになれば今回のサイトは完成になります。

こちらを設定すれば全ての設定は終了となります。

お疲れ様でした。
