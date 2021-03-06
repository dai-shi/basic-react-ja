# ES2015について

Reactでコーディグする際はES2015(=ES6)を使うと便利になることがあります。ES2015は現状ではトランスパイルが必要ですが、後で述べるJSXを使うにはいずれにしてもトランスパイルすることになるため、ES2015を使うことの敷居が相対的に下がっています。

本講座はES2015を学習することを目的とはしませんが、よく使う文法について紹介します。

## constとlet

ES2015では`var`は基本的に使わず、代わりに`const`と`let`を使うことが推奨されます。
 
`const`は再代入しない変数の宣言に用います。`let`は再代入が必要な変数の宣言に用います。再代入とimmutabilityは別物ですので注意が必要です。

```
const x = 1;
let y = 2;
y = 3;

const z = { a: 4, b: 5 };
z.a = 6;
```

## object shorthand

ES2015ではオブジェクトのプロパティ名と値の変数名が同じ場合、省略記法を使うことができます。

```
const foo = 'abc';
const bar = { foo }; // same as { foo: foo }
```

## destructuring object

ES2015ではdestructuring assignmentという簡便な記法が使えます。特にオブジェクトについての記法を紹介します。変数への代入だけでなく、関数のパラメータ宣言でも用います。

```
const obj = { first: 'Ebisu', last: 'JS' };
const { first, last } = obj;
// first === 'Ebisu', last === 'JS'

function printName({ first, last }) { console.log(first, last); }
printName(obj);

// same as
// function printName(name) { console.log(name.first, name.last); }
```

## アロー関数について

`() => ...`という記法はアロー関数と呼ばれます。

アロー関数に関する詳細は、例えば下記を参照してください。  
<https://developer.mozilla.org/ja/docs/Web/JavaScript/Reference/arrow_functions>

`this`に関するスコープの話を置いておくと、アロー関数は通常の関数の省略記法と考えることができます。

```
const f1 = function(x) { console.log(x); };
const f2 = (x) => { console.log(x); };
// f1 and f2 is almost the same
```

アロー関数は`return`文が一つだけの場合は、文そのものを省略できます。

```
const f3 = (x) => { return (x + 1); };
const f4 = (x) => (x + 1);
// f3 and f4 is the same
```

おまけ：カッコの省略も可能ですが、好みの問題でもあります。

```
const f5 = x => x + 1;
```
