# Chapter 4
コンポーネントの更なる掘り下げ

## Chapter 4-1

### renderによる描画
h関数でレンダリング

### JSX
h関数だと入れ子の構造が深くなると分かりにくい．

HTMLを値として直接書き込めるJSXを利用した方が分かりやすい．


## Chapter 4-2

### validator
propsにタイプを設定するのではなく，オブジェクトを設定できる．

そこにrequired, default, validatorなどを設定できる．

### 算術プロパティのGetter, Setter
算出プロパティ(`computed`)でも値の更新をすることが可能．

算出プロパティに直接関数を設定する場合は自動でGetterとして処理が行われる．

Setterは引数を受け取って値をSetすることができる．

### Watcher

値の変更を常に関しするプロパティ．

一つの値を操作した後に複数の値を一斉に更新するような時に使える．


## Chapter 4-3
イベントの深堀

### イベントの流れ
イベントは外側のタグまで伝播される．

イベントが起こる順番は内側->外側

### イベントの修飾子
| 名称| 動き |
|-|-|
|.stop|イベントの伝搬の停止|
|.prevent|イベントのデフォルトアクションの停止|
|.capture|イベントのキャプチャ|
|.self|イベントの発生源の時だけ発火|
|.once|連続してイベントが発生するとき一度だけ発火|

などイベントを操作できる修飾子がある．

### キーイベント
* keypress タイプした時
* keydown　押した時
* keyup 離した瞬間

### 複数キー組み合わせ
複数キーの組み合わせなども可能

* shift シフトキー
* control　コントロールキー
* alt　Altキー
* meta Commandキー
* exact 指定されたキー以外押されていない状態を表す
* left　左クリック
* right　右クリック

例えば`click.shift`などというイベントを設定することが可能

この場合はシフトキーを押した状態でクリックするとイベントが発火


## Chapter 4-4
スロット

### スロットの利用
コンポーネントタグの中に記述されたコンテンツを配置するためのタグ

```html
# App.vue
<HelloWorld>
  This is sample
</HelloWorld>
```

このようにコンポーネントタグの間にコンテンツを配置して，それをコンポーネントの中に反映させるためのもの．

```html
# HelloWorld.vue
<slot />
```
コンポーネント中で`<slot />`を書いたところにコンテンツが反映される．

### 名前付きスロット
スロットはコンポーネントタグの中の記述を全て出力するが，それだと利用する側から細かいタグなどの調整をしなければならず不便．

スロットの中の一部の必要な情報を取り出して利用できるようにするのが名前付きスロット

取り出す側(App.vue)
```html
<template v-slot:name>
```

名前付きスロットの作成(HelloWorld.vue)
```html
<slot name="name" />
```


## Chapter 4-5
トランジションとアニメーション

### フェードイン，フェードアウト
スタイルで指定する．
```html
<style>
.name-enter-active {
  transition: opacity 0.5s
}
.name-leave-active {
  transition: opacity 5.0s;
}
.name-enter {
  opacity: 0;
}
.name-enter-to {
  opacity: 1.0;
}
.name-leave {
  opacity: 1.0;
}
.name-leave-to {
  opacity: 0;
}
</style>
```
`name-enter`, で現れる時，`name-leave`で消える時のスタイルを記述できる．(nameはhtml内のnameタグでつける名前)


### transitionのイベント
* before-enter
* enter
* after-enter
* enter-cancelled
* before-leave
* leave
* after-leave
* leave-cancelled

### transformで動かす
```html
<style>
.name-enter {
  transform: translateX(200px)
}
</style>
```
のようにtransformを設定することが動かすことができる．

### animation
複雑なアニメーションも作成可能．

```css
animation: key-frame time;

@keyframes key-frame {
  0% {
    hoge
  }
  50% {
    fuga
  }
  100% {
    piyo
  }
}
```
このように`@keyframes`で細かい進行状況に応じた処理を行うことができる．
