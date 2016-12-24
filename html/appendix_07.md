# thisless JavaScript

コンポーネントをstateless functionで記述すると、`this`を使う必要がありません。コンポーネントレベルのstateの代わりにReduxなどのsingle storeを使うと、`this`を使う必要がありません。ライフサイクルメソッドも使わずに書けるようになれば、`this`を全く使わずしてReactでコーディングができるはずです。

関数型JavaScriptの世界では、"thisless JavaScript"という表現があるようで、近年注目されてきたようにみえます。ちなみに、Reduxも関数型でthisless JavaScriptです。

`this`はオブジェクト指向では普通に使いますが、関数型では不要です。どちらがよいかは永遠に決着がつかない問題でしょうが、本講座では、関数型指向でstateless function componentを中心に扱いました。

Happy coding!
