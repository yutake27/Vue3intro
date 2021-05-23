# Chapter3
コンポーネント


## Chapter 3-1 コンポーネントの基本

### 3-1
#### **コンポーネントとは**
名前のついた再利用可能なオブジェクト

HTMLタグのようなもの．

例えば`hello`というコンポーネントを作成したら，html中に`<hello />`と書けばhelloコンポーネントを使用することができる．

### 3-3
#### **属性 (props)**
コンポーネントの中の定数のようなもの．


## Chapter 3-2 v属性

### 3-4
#### **v-model**
`<input>`の入力値をVueのdataプロパティの値にバインド

```html
<input v-model="変数">
```
のように使う．

### 3-6
#### **v-on**
イベントのバインド

```
v-on:click="処理"
```

イベント処理のなかにVue3のオブジェクトを使用したい時に使用する．

### 3-9
#### **methods**
メソッドを用意するためのプロパティ

### 3-10
#### **算術プロパティ(computed)**
計算のためのプロパティ

イベントを利用する方法と同じことができる．

算術プロパティとイベントの違いは呼び出されるタイミング．

イベントはユーザーが操作によってイベントが発生するタイミングに呼び出される．これに対して算術プロパティは依存する値が更新された時に実行される．

算術プロパティの方が必要最小限の実行になっていると考えて良い．

算術プロパティの方が負荷が少なくて良いと考えられる．

## Chapter 3-3 プロジェクトによる開発

ここまでは1枚のHTMLファイルに作成してきた．

実際の開発では多数ファイルによる開発を行うので，ここからはプロジェクトを用いた開発を行う．

### プロジェクトの作成
vite_app 作成手順

以下の手順でviteプロジェクトを作成する．

1. make project

    ```
    npm init vite-app vite_app
    ```
2. install

    ```
    cd vite_app
    npm install
    ```

3. run

    ```
    npm run dev
    ```

4. build

    ```
    npm run build
    ```

### プロジェクトの基本構造

* vite_app内のファイル
  * index.html　-  大元のhtml
  * package.json - プロジェクトの設定情報
  * package-lock.json - プロジェクトの設定に関するファイル

* vite_app内のフォルダ
  * public
    * 外部に公開するファイル類
  * src
    * main.js - アプリケーションのプログラム
    * App.vue アプリケーションで使うコンポーネントファイル
    * assets
      * logo.png - ロゴのイメージ
    * components -コンポーネントファイルがまとまったフォルダ
  * node_modules - プロジェクトで使うパッケージ類
  * dist - ビルドして生成された公開ファイル類


### App.vue

#### **`<template>`タグ**
コンポーネントのテンプレートの内容を書く

#### **export default**
他のスクリプトからimportする際にimportする場所を表している．


### 子コンポーネントから親コンポーネントに値を渡す

親コンポーネントから子コンポーネントはそのまま渡せる．

逆に子コンポーネントから親コンポーネントに値を渡すときは少し複雑．

```JavaScript
this.$emit(result-event, '引数の値')
```

のように子コンポーネントからはイベントを送る．

それに対して親コンポーネントはイベントを受け取る．

```html
<HelloWorld v-on:result-event="doAction">
```
`doAction`には関数を設定．

```JavaScript
methods: {
  doAction(arg) {
    this.result = arg
  }
}
```

### テンプレート参照
テンプレートに用意されているHTMLを直接操作したい時に使う．

テンプレートに`ref="名前"`のようにrefをつけておき，それをスクリプト側で受け取る．

```JavaScript
this.$refs."名前".innerHTML = 'hoge'
```

このようにスクリプト側からHTMLを操作できる．

ただしこれはVue3によって構築されている内部構造を破壊する危険もあるので，必要最小限の利用にする．


## Chapter 3-4

### ローカルストレージ
キャッシュにデータを保存しておける．

```JavaScript
変数 = localStorage.getItem(key)
localStorage.setItem('name', value)
```

のように使える．便利そう．