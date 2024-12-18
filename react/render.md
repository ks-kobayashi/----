# 条件レンダリング
JSXの中に条件付きでコンポーネントなどを変えたい場合、三項演算子を使う場合が多い。
JSXの中の{}としてjsの式を埋め込める。  
```tsx
function LoginStatus({ isLoggedIn }) {
  return <div>
      {isLoggedIn ? <p>ログイン中</p> : <p>未ログイン</p>}
  </div>;
}
```

# 配列レンダリング
基本map関数を使うこと。  
コンポーネントを返す関数を入れる。  
```tsx
function SimpleList() {
  const colors = ['赤', '青', '緑'];

  return <ul>
      {colors.map((color, i) => (
        <li key={i}>{color}</li>
      ))}
  </ul>;
}
```

## keyとは？？？？

配列表示の時、Reactがどの要素が変更されたかを識別するための目印として使われる
↑とはなにか
通常、useStateなどで配列が更新されたとき、配列全体の再レンダリングをするが、keyを設定することによりkeyによって識別された変更が加わった要素のみを再レンダリングしてくれる。
階層ごとにユニークな値が必要。




