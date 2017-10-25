# 関数型のコーディング

Reactでコンポーネントを書く際は関数型のコーディングの方が楽な場合が多いです。

関数型プログラミングも奥が深いですが、本講座でよく使う文法について紹介します。

## pure function

pure functionとは、一般的に副作用がない関数のことです。

```
const pureFunc = (x) => { let y = x + 1; return y; };

let y;
const notPure = (x) => { y = x + 1; return y; };

const notPure2 = (x) => { console.log('foo'); return x + 1; };
```

## logical operators

論理演算子には、`&&`, `||`, `!`の3つがあります。

`x && y`という表現は、xがfalsyの場合はxであり、そうでない場合はyになります。falsyとは、`false`,`null`,`0`,`''`などの値です。[詳しくはこちら](https://developer.mozilla.org/ja/docs/Glossary/Falsy)。

`x || y`という表現は、xがfalsyの場合はyであり、そうでない場合はxになります。

`!x`という表現は、xがfalsyの場合は`true`であり、そうでない場合は`false`になります。

ポイント：`x`は真偽値(boolean)でなくてもよいです

```
0 && 1
// 0

1 && 2
// 2

0 || 1
// 1

1 || 2
// 1

!0
// true

!1
// false
```

## ternary operator

三項演算子もよく使います。うまく使えば便利です。

`x ? y : z`という表現は、xがfalsyの場合はzであり、そうでない場合はyになります。

```
0 ? 1 : 2
// 2

3 ? 4 : 5
// 4
```

## filter

Array.filterは配列から部分配列を作る関数です。[参照](https://developer.mozilla.org/ja/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)

引数で与えたテスト関数がtruthy(つまりfalsyでない)を返す要素の配列を返します。配列は新しく作られますが、要素オブジェクトはコピーされません。
テスト関数にはアロー関数を使うと簡便に書くことができます。

```
[1, 2, 3, 4].filter((x) => (x > 2))
// [3, 4]

['a', 'ab', 'abc', 'abcd'].filter((x) => (x.length <= 2))
// ['a', 'ab']

[0, 1, 2, '', 'a', false, true].filter((x) => (x));
// [1, 2, 'a', true]
```

## map

Array.mapは配列から要素ごとに変換して新しい配列を作る関数です。[参照](https://developer.mozilla.org/ja/docs/Web/JavaScript/Reference/Global_Objects/Array/map)

引数で与えられた変換関数で返される値を要素にもつ配列を返します。配列は新しく作られます。要素数は変化しません。

```
[1, 2, 3, 4].map((x) => (x * 2))
// [2, 4, 6, 8]

['a', 'ab', 'abc', 'abcd'].map((x) => (x.length))
// [1, 2, 3, 4]

[1, 2, 'a', 'b'].map((x) => ('あ' + x))
// ['あ1', 'あ2', 'あa', 'あb']
```
