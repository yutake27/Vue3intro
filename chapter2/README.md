# Chapter2

Vue3の基本

htmlに直接コードを書く場合の書き方

## Section 2-1
### 2-2
#### mounted

Vue3オブジェクトがWebページに組み込まれた際に実行される処理

### 2-3
#### created

アプリケーションオブジェクトが生成された際に実行される処理

## Section 2-2

### 2-4
#### v-html
HTMLコードを変数に設定して，htmlに埋め込む

## Section 2-3

### 2-18
#### v-bind
タグの属性にVue3の変数を設定したい時に使用．

```html
v-bind:name="message"
```

のように使用する．

nameはタグの名前でmessageが変数．

### 2-23
#### v-if v-else
変数の値を条件とする．

### 2-25
#### v-for
for文
```html
<tr v-for="item in items">
    <td>{{ items.name }}</td>
</tr>
```
`items`というリストから値を取り出し繰り返し処理を行う．

### 2-29
#### `<template>`
`v-for`や`v-if`などの制御文を使用する際には分かりやすくするために`<template>`というタグを使用した方が良い．
