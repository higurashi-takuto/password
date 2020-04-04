# password
GitHub Pages などの静的サイトのホスティングサービスで擬似的にパスワード認証をつけるものです。

## DEMO
[リンク](https://higurashi-takuto.github.io/password/)

※パスワードは `password` です。

## ファイル
- index.html  
パスワード入力画面です。  
[サンプル](https://higurashi-takuto.github.io/password/)

- check.html  
認証に使用するハッシュ値を確認するためのページです。  
[サンプル](https://higurashi-takuto.github.io/password/check.html)

- style.css  
スタイルシートで `index.html` / `check.html` 共通のものです。

- padlock.svg  
ファビコン用画像です。ダークモード対応しています。

- sha256.js  
SHA-256 を使用するためのライブラリです。
[jsSHA](https://github.com/Caligatio/jsSHA) を利用しています。

- 5e884898da28047151d0e56f8dc6292773603d0d6aabbdd62a11ef721d1542d8/  
パスワード突破後にアクセスされるディレクトリです。

## 使い方 / 仕組み
ハッシュ化されたパスワードをそのままディレクトリ名に利用し、URL の存在の有無で認証を行なっています。

この方法のデメリットとして URL が知られる / ディレクトリリストが取得される という方法によっても突破されてしまうため、URL の共有やサーバの設定に注意しましょう。

ハッシュ化には SHA-256 を使用しており、入力に対するハッシュ値の確認には [check.html](https://higurashi-takuto.github.io/password/check.html) が利用できます。ここで取得できるハッシュ値をディレクトリ名に付けましょう。

## 参考リポジトリ
[matteobrusa / Password-protection-for-static-pages](https://github.com/matteobrusa/Password-protection-for-static-pages)