# React基礎

レッスン

- [Lesson 01](lesson_01.md): 環境構築
- [Lesson 02](lesson_02.md): ES2015について
- [Lesson 03](lesson_03.md): 関数型の書き方
- [Lesson 04](lesson_04.md): 初めてのコンポーネント
- [Lesson 05](lesson_05.md): 初めてのinline style
- [Lesson 06](lesson_06.md): 初めてのprops
- [Lesson 07](lesson_07.md): 配列からの展開
- [Lesson 08](lesson_08.md): フォームの定義
- [Lesson 09](lesson_09.md): フォームによるデータ追加
- [Lesson 10](lesson_10.md): 総合課題「目的特化型電卓を作ってみよう」

おまけ

- [Appendix 01](appendix_01.md): 様々なコンポーネントの書き方
- [Appendix 02](appendix_02.md): コンポーネントのstate
- [Appendix 03](appendix_03.md): コンポーネントのライフサイクルメソッド
- [Appendix 04](appendix_04.md): JSX vs. createElement
- [Appendix 05](appendix_05.md): PropTypes
- [Appendix 06](appendix_06.md): presentational/container components
- [Appendix 07](appendix_07.md): thisless JavaScript

メモ

- Reactとは
  - HTMLを直接は使わずJavaScriptで動的に生成する仕組み
  - JavaScriptのエコシステム(テストツールなど)が使える
  - コンポーネント指向で、独立した部品を組み合わせて作る
- Virtual DOMとは 
  - Reactが内部で使っている仕組み
  - JavaScriptで生成したDOMを模倣したデータ構造で差分計算をして、実際のDOMに反映させるため、処理が高速になる
