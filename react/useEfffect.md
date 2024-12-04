useEffectから書いてく

# useEffect
コンポーネントの「副作用」を扱う。 
副作用とは→UIの表示以外に必要なデータフェッチやリスナ初期化などのロジック。 
この場合、TestComponentが描画されたタイミングで必ずログが出る。

```tsx
function TestComponent() {
    useEffect(() => {
        console.log('コンポーネントが描画されました！');
    });
    return <h1>あいうえお</h1>;
}
```


再描画も対象なので、ボタンが押されるたびにログが出る。
```tsx
function TestComponent() {
    const [count, setCount] = useState(0);
    useEffect(() => {
        console.log('描画されました！');
    };
    return <div>
        <h1>Count: {count}</h1>
        <button onClick={() => setCount(count + 1)}>++</button>
    </div>;
}
```

これを防止するために、依存配列を書く。
useEffectの第2引数に配列を入れると、配列に入れたstateの値が更新されたときのみ、useEffectの中の関数が実行されるようになる。
何も入れないと毎回実行される。空の配列を入れると初回描画時しか実行されない。←これがめっちゃややこしい
第2引数を省略すると毎回実行され[]を入れると初回しか実行されないということだ。

# なんか2回実行される
開発サーバーのStrictModeの仕様らしい。コンポーネントが純粋関数になっていることを保証するためらしい。  
「純粋関数なら2回実行しても動作に影響ないはずだよな？」という思想。2回実行されても問題ない関数にしなさいとのこと。  