# React基礎

レッスン

- [Lesson 01](lesson-01.md): 環境構築
- [Lesson 02](lesson-02.md): ES2015について
- [Lesson 03](lesson-03.md): 関数型の書き方
- [Lesson 04](lesson-04.md): 初めてのコンポーネント
- [Lesson 05](lesson-05.md): 初めてのinline style
- [Lesson 06](lesson-06.md): 初めてのprops
- [Lesson 07](lesson-07.md): 配列からの展開
- [Lesson 08](lesson-08.md): フォームの定義
- [Lesson 09](lesson-09.md): フォームによるデータ追加
- [Lesson 10](lesson-10.md): 総合課題「目的特化型電卓を作ってみよう」

おまけ

- [Appendix 01](appendix-01.md): 様々なコンポーネントの書き方
- [Appendix 02](appendix-02.md): コンポーネントのstate
- [Appendix 03](appendix-03.md): コンポーネントのライフサイクルメソッド
- [Appendix 04](appendix-04.md): JSX vs. createElement
- [Appendix 05](appendix-05.md): PropTypes
- [Appendix 06](appendix-06.md): presentational/container components
- [Appendix 07](appendix-07.md): thisless JavaScript

メモ

- Reactとは
  - HTMLを直接は使わずJavaScriptで動的に生成する仕組み
  - JavaScriptのエコシステム(テストツールなど)が使える
  - コンポーネント指向で、独立した部品を組み合わせて作る
- Virtual DOMとは 
  - Reactが内部で使っている仕組み
  - JavaScriptで生成したDOMを模倣したデータ構造で差分計算をして、実際のDOMに反映させるため、処理が高速になる
