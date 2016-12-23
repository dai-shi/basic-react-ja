# React基礎

レッスン

- [Lesson 01](lesson_01): 環境構築
- [Lesson 02](lesson_02): ES2015について
- [Lesson 03](lesson_03): 関数型の書き方
- [Lesson 04](lesson_04): 初めてのコンポーネント
- [Lesson 05](lesson_05): 初めてのinline style
- [Lesson 06](lesson_06): 初めてのprops
- [Lesson 07](lesson_07): 配列からの展開
- [Lesson 08](lesson_08): フォームの定義
- [Lesson 09](lesson_09): フォームによるデータ追加
- [Lesson 10](lesson_10): 総合課題「目的特化型電卓を作ってみよう」

おまけ

- [Appendix 01](appendix_01): 様々なコンポーネントの書き方
- [Appendix 02](appendix_02): コンポーネントのstate
- [Appendix 03](appendix_03): コンポーネントのライフサイクルメソッド
- [Appendix 04](appendix_04): JSX vs. createElement
- [Appendix 05](appendix_05): PropTypes
- [Appendix 06](appendix_06): presentational/container components
- [Appendix 07](appendix_07): thisless JavaScript

メモ

- Reactとは
  - HTMLを直接は使わずJavaScriptで動的に生成する仕組み
  - JavaScriptのエコシステム(テストツールなど)が使える
  - コンポーネント指向で、独立した部品を組み合わせて作る
- Virtual DOMとは 
  - Reactが内部で使っている仕組み
  - JavaScriptで生成したDOMを模倣したデータ構造で差分計算をして、実際のDOMに反映させるため、処理が高速になる
